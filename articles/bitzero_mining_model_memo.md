# Bit-zero: Mining Model Memo

### Worksheets

1. **Inventory** contains miner model, miner hashrate and miner power consumption
2. **Activation** contains the miners organized by batch dates and quantities as per their activation date. It also contains an estimated depreciation time life (3-years).
3. **Block Reward** contains the given block reward according to the halving period. The last recorded halving dates May 10, 2024.
4. **avgHashrate** contains the realized average daily hashrate for the bitcoin network expressed in TH. It also contains the standard deviation for the realized hashrate values up to July 25, 2024. Finally, it also includes projected hashrates values for July 26, 2024 - September 6, 2025.
5. **Bitcoin Price** contains the realized closing price of bitcoin up to July 25, 2024 and the projected closing price for July 26, 2024 - September 6, 2025. The projected price was calculated using the daily standard deviation and Exponential Moving Average (EMA-30).
6. **Electricity** contains the average kwh price. Currently priced at 16 cents.
7. **Model** contains the completed mining model, including realized dates and projected revenues (lack thereof).

### Formulas

1. **Main** = (((Equipment hashrate * # of miners)/ Network hashrate)* block reward * daily blocks mined (144) * Bitcoin price) - ((Equipment power consumption * # of miners * 24 * Electricity price)/ 1,000)

    *where* 24 = hours/day

### Notes from the author

1. I believe the accounting and public practice industry needs a more accurate method of calculating miner depreciation value. ASIC miners (in particular), are computers that do one thing: hash.
