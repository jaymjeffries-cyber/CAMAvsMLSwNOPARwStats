# Statistical Features Documentation

## CAMA Parcel Match Statistics

The application now includes comprehensive statistics showing how many CAMA parcels were found in the MLS data.

### Overall Statistics

The tool displays three key metrics:

1. **Total CAMA Parcels**: The total number of parcels in your CAMA assessment data
2. **Found in MLS**: How many of those CAMA parcels appear in the MLS sales data
3. **Match Rate**: The percentage of CAMA parcels that were found in MLS

**Formula**: Match Rate = (Found in MLS / Total CAMA Parcels) × 100

### Match Rate by City

The application provides a detailed breakdown by city, showing:

- **City**: Name of the city
- **Total_CAMA_Parcels**: Number of parcels in CAMA for that city
- **Matched_Parcels**: Number of those parcels found in MLS
- **Not_Matched**: Number of parcels not found in MLS (Total - Matched)
- **Match_Rate**: Percentage match rate for that city

### Visualizations

Two charts are provided:

1. **Top 10 Cities by Total CAMA Parcels**: 
   - Stacked bar chart showing matched vs. not matched parcels
   - Helps identify which cities have the most properties

2. **Match Rate by City (Top 10)**:
   - Bar chart showing the match rate percentage for each city
   - Helps identify which cities have better MLS coverage

### Export Options

You can download the city-level statistics as a CSV file for further analysis in Excel or other tools.

## Use Cases

### Quality Assurance
- Verify that MLS data covers your assessment areas adequately
- Identify cities with low match rates that may need attention

### Coverage Analysis
- Understand which areas have good MLS sales data
- Plan data collection efforts for underrepresented areas

### Reporting
- Generate reports on MLS data completeness
- Track coverage improvements over time

### Trend Analysis
- Compare match rates across different time periods
- Identify seasonal or market-driven patterns

## Understanding the Results

### High Match Rate (>80%)
Indicates strong MLS coverage for that area. Most CAMA parcels have corresponding MLS sales records.

### Medium Match Rate (50-80%)
Moderate coverage. Some parcels in CAMA don't have MLS records, which could be due to:
- Properties that haven't sold recently
- Properties sold outside the MLS system
- Data synchronization timing differences

### Low Match Rate (<50%)
Limited coverage. Possible reasons:
- Rural or low-transaction areas
- Properties with restricted sales (private sales, auctions)
- Data quality or timing issues
- Different property types (commercial vs. residential)

## Technical Notes

### Data Requirements

For city-level statistics to work:
- **CAMA data must include a 'City' column** OR
- City information will be derived from matched MLS records

If CAMA doesn't have City information, the app will show statistics for matched parcels only.

### Handling Missing Data

- Cities with no matches show 0% match rate
- Empty or null city values are excluded from the breakdown
- The overall statistics include all parcels regardless of city data

### Performance

The statistical calculations are performed in-memory and should be fast even for large datasets (100K+ parcels). If you experience slowdowns:
- Check your data file sizes
- Consider filtering data by date range before upload
- Use the most recent CAMA extract

## Example Interpretation

**Scenario**: You upload CAMA data with 50,000 parcels and MLS data with 8,500 sales.

**Results**:
- Total CAMA Parcels: 50,000
- Found in MLS: 8,500
- Match Rate: 17.00%

**City Breakdown** (example):
| City      | Total_CAMA | Matched | Not_Matched | Match_Rate |
|-----------|------------|---------|-------------|------------|
| Canton    | 15,000     | 4,200   | 10,800      | 28.00%     |
| Massillon | 8,000      | 1,800   | 6,200       | 22.50%     |
| Alliance  | 5,000      | 950     | 4,050       | 19.00%     |

**Interpretation**: 
- Overall, about 17% of assessed parcels have MLS sales records
- Canton has the highest match rate (28%), suggesting more active sales or better MLS participation
- This is normal for annual sales data - most properties don't sell every year
- A 15-25% annual match rate is typical for residential property markets

## Frequently Asked Questions

### Why is my match rate low?

Low match rates are often normal and expected:
- Most properties don't sell every year (typical turnover is 5-8% annually)
- If your MLS data covers one year, expect ~5-15% match rate
- Commercial, vacant land, and rental properties have lower turnover

### What's a "good" match rate?

This depends on your data timeframe:
- **1 year of MLS data**: 5-15% is typical
- **3 years of MLS data**: 15-35% is typical  
- **5+ years of MLS data**: 30-50% is typical
- **All-time MLS data**: 50-80% is possible in active markets

### Why do some cities have 0% match rate?

Possible reasons:
- Very small cities with few recent sales
- City name mismatches between CAMA and MLS
- Properties outside MLS system (FSBO, auctions, foreclosures)

### Can I improve my match rate?

Yes, by:
- Using a longer timeframe for MLS data
- Ensuring city names are standardized
- Verifying parcel ID formats match
- Including all property types in MLS data

## Additional Resources

For more information on data quality and validation, see the main README.md file.

For technical support or questions about the statistics, open an issue on the GitHub repository.
