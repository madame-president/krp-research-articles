# API request for gathering Lightning Node data for audit purposes

[Mempool Documentation](https://mempool.space/docs/api/rest#get-node-stats)

## Procedure

**Following the documentation provided, we created the following python script:**

```
import requests

# Mempool URL
url = "https://mempool.space/api/v1/lightning/nodes/0230b207b3385feddb1ed18d5c7a808015aeb668aaf9bf980bee62465a382112c1"

# API request
response = requests.get(url)

# Request check
if response.status_code == 200:
    # Get JSON response
    data = response.json()
    
    # Relevant data for audit
    relevant_data = {
        "public_key": data.get("public_key"),
        "alias": data.get("alias"),
        "first_seen": data.get("first_seen"),
        "updated_at": data.get("updated_at"),
        "country": data.get("country", {}).get("en"),
        "active_channel_count": data.get("active_channel_count"),
        "capacity": data.get("capacity"),
        "open_channel_count": data.get("opened_channel_count"),
        "closed_channel_count": data.get("closed_channel_count"),
        "custom_records": data.get("custom_records"),
    }
    
    # Print to terminal
    for key, value in relevant_data.items():
        print(f"{key}: {value}")
else:
    print(f"Failed to retrieve data: {response.status_code}")
```

**After a succesful request is made, all the JSON data is exported to an .xlsx file:**

```
import requests
import pandas as pd
from openpyxl import Workbook
from datetime import datetime

# API Request
def get_data(pubkey):
    url = f"https://mempool.space/api/v1/lightning/nodes/{pubkey}"
    
    response = requests.get(url)
    
    if response.status_code == 200:
        data = response.json()
        audit_data = {
            "public_key": data.get("public_key"),
            "alias": data.get("alias"),
            "first_seen": data.get("first_seen"),
            "updated_at": data.get("updated_at"),
            "country": data.get("country", {}).get("en"),
            "active_channel_count": data.get("active_channel_count"),
            "capacity": data.get("capacity"),
            "open_channel_count": data.get("opened_channel_count"),
            "closed_channel_count": data.get("closed_channel_count"),
            "custom_records": data.get("custom_records"),
        }
        return audit_data
    else:
        print(f"Failed to retrieve data for pubkey {pubkey}: {response.status_code}")
        return None

# Unix to readable time format
def convert_timestamp(timestamp):
    return datetime.utcfromtimestamp(timestamp).isoformat() if timestamp else None

# Read input file
input_file_path = 'input/nodes.xlsx' # update according to file name
df = pd.read_excel(input_file_path)

# Create new file
output_wb = Workbook()
output_wb.remove(output_wb.active)

# Check row by row
for index, row in df.iterrows():
    alias = row['Alias']
    pubkey = row['Pubkey']
    
    if pd.notna(pubkey):  # Check if pubkey is not NaN
        data = get_data(pubkey)
        if data:
            sheet_name = pubkey[:10]  # First 10 digits of the pubkey
            sheet = output_wb.create_sheet(title=sheet_name)
            
            # Write audit data to new file
            for idx, (key, value) in enumerate(data.items(), start=1):
                # Convert non-stringifiable values to strings
                if isinstance(value, (dict, list)):
                    value = str(value)
                sheet[f"A{idx}"] = key
                sheet[f"B{idx}"] = value

                # Convert timestamp
                if key in ["first_seen", "updated_at"] and value is not None:
                    iso_format_value = convert_timestamp(int(value))
                    sheet[f"C{idx}"] = iso_format_value

# Save new file while keeping original file
output_file_path = input_file_path.replace('.xlsx', '_responses.xlsx')
output_wb.save(output_file_path)

print(f"Responses saved to {output_file_path}")
```