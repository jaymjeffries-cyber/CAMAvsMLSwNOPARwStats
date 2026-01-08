# Statistics Output Examples

## What You'll See in the App

### Overall Match Rate Section

```
📊 CAMA Parcel Match Statistics
Analysis of which CAMA parcels were found in the MLS data

┌─────────────────────┬──────────────────┬─────────────────┐
│ Total CAMA Parcels  │  Found in MLS    │   Match Rate    │
│      50,000         │     8,500        │     17.00%      │
└─────────────────────┴──────────────────┴─────────────────┘
```

**Interpretation**: Of the 50,000 parcels in your CAMA assessment database, 8,500 appear in the MLS sales data (17% match rate).

---

### City-Level Breakdown Table

```
Match Rate by City

┌──────────────┬──────────────────┬─────────────────┬───────────────┬────────────┐
│ City         │ Total_CAMA       │ Matched_Parcels │ Not_Matched   │ Match_Rate │
│              │ _Parcels         │                 │               │            │
├──────────────┼──────────────────┼─────────────────┼───────────────┼────────────┤
│ Canton       │     15,000       │      4,200      │    10,800     │   28.00%   │
│ Massillon    │      8,000       │      1,800      │     6,200     │   22.50%   │
│ Alliance     │      5,000       │        950      │     4,050     │   19.00%   │
│ North Canton │      4,500       │        720      │     3,780     │   16.00%   │
│ Louisville   │      3,200       │        480      │     2,720     │   15.00%   │
│ Hartville    │      2,800       │        392      │     2,408     │   14.00%   │
│ Canal Fulton │      2,500       │        325      │     2,175     │   13.00%   │
│ Minerva      │      2,000       │        240      │     1,760     │   12.00%   │
│ Navarre      │      1,800       │        198      │     1,602     │   11.00%   │
│ Beach City   │      1,200       │        120      │     1,080     │   10.00%   │
└──────────────┴──────────────────┴─────────────────┴───────────────┴────────────┘

[📥 Download City Statistics (CSV)]
```

---

### Visualizations

**Chart 1: Top 10 Cities by Total CAMA Parcels**
```
Canton       ████████████████░░░░ (4,200 matched, 10,800 not matched)
Massillon    ████████░░░░░░░░░░░░ (1,800 matched, 6,200 not matched)
Alliance     █████░░░░░░░░░░░░░░░ (950 matched, 4,050 not matched)
North Canton ████░░░░░░░░░░░░░░░░ (720 matched, 3,780 not matched)
Louisville   ███░░░░░░░░░░░░░░░░░ (480 matched, 2,720 not matched)
```
*Blue = Matched, Gray = Not Matched*

**Chart 2: Match Rate by City (Top 10)**
```
Canton       ████████████████████████████ 28.00%
Massillon    ██████████████████████▌      22.50%
Alliance     ███████████████████          19.00%
North Canton ████████████████             16.00%
Louisville   ███████████████              15.00%
Hartville    ██████████████               14.00%
Canal Fulton █████████████                13.00%
Minerva      ████████████                 12.00%
Navarre      ███████████                  11.00%
Beach City   ██████████                   10.00%
```

---

## Downloaded CSV Format

When you download the city statistics, you'll get a CSV file like this:

```csv
City,Total_CAMA_Parcels,Matched_Parcels,Not_Matched,Match_Rate
Canton,15000,4200,10800,28.00
Massillon,8000,1800,6200,22.50
Alliance,5000,950,4050,19.00
North Canton,4500,720,3780,16.00
Louisville,3200,480,2720,15.00
Hartville,2800,392,2408,14.00
Canal Fulton,2500,325,2175,13.00
Minerva,2000,240,1760,12.00
Navarre,1800,198,1602,11.00
Beach City,1200,120,1080,10.00
```

This can be opened in Excel for further analysis, pivot tables, or custom charts.

---

## Real-World Example

### Scenario
You're a county assessor wanting to validate MLS coverage for the 2024 tax year. You have:
- CAMA database: All 52,437 residential parcels in the county
- MLS data: All 2024 sales (3,829 transactions)

### Results After Running Comparison

**Overall Statistics:**
- Total CAMA Parcels: 52,437
- Found in MLS: 3,829
- Match Rate: 7.30%

**City Breakdown (Top 5):**

| City         | CAMA Parcels | MLS Sales | Match Rate | Status     |
|--------------|--------------|-----------|------------|------------|
| Canton       | 18,500       | 892       | 4.82%      | ⚠️ Low     |
| Massillon    | 9,200        | 445       | 4.84%      | ⚠️ Low     |
| Alliance     | 6,100        | 312       | 5.11%      | ✅ Normal  |
| North Canton | 5,800        | 892       | 15.38%     | ✅ High    |
| Louisville   | 3,400        | 223       | 6.56%      | ✅ Normal  |

### Interpretation

**Overall 7.30% Match Rate:**
- ✅ **Normal** for one year of sales data
- Typical residential turnover is 5-10% annually
- Within expected range for 2024 sales

**Canton & Massillon (4.8%):**
- ⚠️ Slightly below average
- Possible reasons:
  - More rental properties (lower turnover)
  - Older housing stock
  - Economic factors
- **Action**: Verify MLS includes all sale types

**North Canton (15.38%):**
- ✅ Excellent coverage!
- High turnover suggests:
  - Desirable market
  - Newer developments
  - Active real estate market
- **Action**: None needed - great data quality

### Using This Information

1. **For Data Quality**: Identify gaps in MLS coverage
2. **For Market Analysis**: Understand which areas are actively trading
3. **For Reporting**: Document data completeness to stakeholders
4. **For Planning**: Focus resources on low-coverage areas

---

## Tips for Using Statistics

### Comparing Time Periods
Run the tool monthly or quarterly and compare match rates to identify trends:
```
Q1 2024: 6.2%  → Normal winter slowdown
Q2 2024: 9.8%  → Spring market pickup
Q3 2024: 7.4%  → Summer normalization  
Q4 2024: 5.1%  → Holiday season slowdown
```

### Setting Benchmarks
Establish what's "normal" for your market:
- Small cities (< 5,000 parcels): 8-15% annual match rate
- Medium cities (5,000-15,000): 6-12% annual match rate
- Large cities (> 15,000): 4-8% annual match rate

### Investigating Anomalies
If a city shows 0% or unusually low match rate:
1. Check for city name differences (e.g., "St. Louis" vs "Saint Louis")
2. Verify parcel ID formats match
3. Confirm date ranges align
4. Look for data entry errors

---

## Questions?

See **STATISTICS_GUIDE.md** for comprehensive documentation on interpreting these statistics.
