# MLS vs CAMA Data Comparison Tool

A Streamlit web application for comparing MLS (Multiple Listing Service) and CAMA (Computer Assisted Mass Appraisal) property data to identify discrepancies and perfect matches.

## Features

- 📊 **Data Comparison**: Compare property data between MLS and CAMA systems
- 🔍 **Discrepancy Detection**: Identify missing records and value mismatches
- ✅ **Perfect Match Tracking**: Track properties with perfectly matching data
- 📈 **Match Rate Statistics**: Analyze CAMA parcel coverage in MLS data
  - Overall match rate (number and percentage)
  - City-level breakdown with visualizations
  - Exportable statistics reports
- 🔗 **Hyperlinked Reports**: Generated Excel reports include clickable links to:
  - Stark County property records
  - Zillow property listings
- 📈 **Visual Analytics**: View mismatch breakdowns by field
- ⚙️ **Configurable**: Adjust numeric tolerance and comparison settings

## Quick Start

### Deploy to Streamlit Cloud (Recommended)

1. **Fork this repository** to your GitHub account

2. **Go to [Streamlit Cloud](https://streamlit.io/cloud)**

3. **Click "New app"** and select:
   - Repository: Your forked repository
   - Branch: `main`
   - Main file path: `streamlit_app.py`

4. **Click "Deploy"** and wait for the app to launch

### Run Locally

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run streamlit_app.py
```

The app will open in your browser at `http://localhost:8501`

## Usage

1. **Enter WindowId** (optional but recommended):
   - Visit the [Stark County iasWorld](https://iasworld.starkcountyohio.gov/iasworld/)
   - Search for any property
   - Copy the `windowId` from the URL
   - Paste it in the sidebar

2. **Upload Data Files**:
   - Upload your MLS Excel file (.xlsx or .xls)
   - Upload your CAMA Excel file (.xlsx or .xls)

3. **Configure Settings** (optional):
   - Adjust numeric tolerance for comparisons
   - Enable/disable zero value skipping

4. **Run Comparison**:
   - Click the "Run Comparison" button
   - Review results in the interactive tables
   - View match rate statistics:
     - Overall CAMA parcel match rate
     - City-level breakdown and visualizations
   - Download Excel reports with hyperlinks
   - Export city statistics as CSV

## Data Requirements

### MLS Data Columns
- `Parcel Number` - Unique identifier
- `Above Grade Finished Area`
- `Bedrooms Total`
- `Bathrooms Full`
- `Bathrooms Half`
- `Below Grade Finished Area`
- `Cooling`
- `Address`, `City`, `State or Province`, `Postal Code`
- `Listing #`
- `Closed Date`

### CAMA Data Columns
- `PARID` - Unique identifier
- `NOPAR` - Additional identifier
- `CITYNAME` (or `City`) - City name for statistics
- `SFLA` - Square feet living area
- `RMBED` - Bedrooms
- `FIXBATH` - Full bathrooms
- `FIXHALF` - Half bathrooms
- `RECROMAREA`, `FINBSMTAREA`, `UFEATAREA` - Basement areas
- `HEAT` - Heating/cooling system
- `SALEKEY`

## Comparison Logic

The tool performs three types of comparisons:

1. **Direct Field Comparisons**: One-to-one matching of MLS and CAMA fields
2. **Sum Comparisons**: MLS field compared to sum of multiple CAMA fields
3. **Categorical Comparisons**: Text-based matching with expected numeric values

## Output Reports

Four Excel reports are generated:

1. **Missing in CAMA**: Properties in MLS but not in CAMA
2. **Missing in MLS**: Properties in CAMA but not in MLS
3. **Value Mismatches**: Properties with data discrepancies
4. **Perfect Matches**: Properties with all fields matching

Plus one CSV statistics report:

5. **City Match Statistics**: Match rate analysis by city

All Excel reports include:
- Clickable Parcel IDs linking to county records
- Clickable addresses linking to Zillow
- Detailed field-by-field comparison data

The city statistics CSV includes:
- Total CAMA parcels per city
- Number of matched parcels per city
- Match rate percentage by city

## Configuration Files

### requirements.txt
Lists all Python dependencies needed for the app.

### .streamlit/config.toml
Optional Streamlit configuration for appearance and behavior.

## Repository Structure

```
.
├── streamlit_app.py          # Main Streamlit application
├── mls_cama_comparison.py    # Original Python script (for local use)
├── requirements.txt          # Python dependencies
├── .streamlit/
│   └── config.toml          # Streamlit configuration
└── README.md                # This file
```

## Troubleshooting

### "Column not found" errors
- Verify your Excel files have the expected column names
- Check for extra spaces in column headers
- Ensure column names match the configuration exactly

### Hyperlinks not working
- Verify the WindowId is correct
- Check that the Parcel IDs in your data are valid

### App running slowly
- Large datasets may take time to process
- Consider filtering your data before upload

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the MIT License.

## Support

For issues or questions:
1. Check the troubleshooting section
2. Review the data requirements
3. Open an issue on GitHub

## Version History

- **v1.0** - Initial release with core comparison functionality
- **v1.1** - Added NOPAR column support
- **v1.2** - Streamlit web interface implementation
- **v1.3** - Added CAMA parcel match rate statistics
  - Overall match rate calculation
  - City-level breakdown and visualizations
  - Exportable statistics reports
