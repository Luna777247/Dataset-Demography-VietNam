# AI Coding Assistant Instructions for Vietnamese Demography Analysis Project

## Project Overview
This is a Vietnamese demography research project analyzing population trends from 1955-2050 using mathematical ecological models. The project focuses on demographic transition, aging population, urbanization impacts, and population forecasting using statistical models. All analysis and reporting is conducted in Vietnamese (Tiếng Việt).

## Architecture & Data Flow
- **0_rawdata/**: Raw datasets from international organizations (World Bank, IMF, FAO, UNDP, UNCTAD, GSO, WPP)
- **1_Mô hình toán sinh thái/**: Statistical modeling and analysis outputs, including Vietnamese reports and visualization directories
- **2_Trực quan hóa thông tin/**: Consolidated datasets and data collection documentation

Data flows: Raw international sources → Consolidation (`vietnam_consolidated_final_1955_2025.csv`) → Statistical analysis → Forecasting models → Vietnamese reports & visualizations.

## Key Technologies & Libraries
- **Python ecosystem**: pandas, numpy, matplotlib, seaborn, scipy, statsmodels, sklearn
- **Modeling approaches**: Logistic growth models, OLS regression, ARIMA time series, sensitivity analysis
- **Data formats**: CSV files with 35+ demographic indicators (population, median age, fertility rate, urbanization, GDP, HDI, etc.)
- **Output formats**: Vietnamese Markdown reports, PNG visualizations

## Critical Developer Workflows

### Data Processing Pipeline
- **Raw data loading**: Use `pd.read_csv(path, encoding='utf-8')` for international data sources
- **Vietnam filtering**: Filter WPP data by `Location == 'Viet Nam'` and ISO3 code 'VNM'
- **Data consolidation**: Merge datasets by Year, handle missing values with linear interpolation
- **Quality validation**: Cross-reference with GSO data, check value ranges, remove outliers using IQR method

### Statistical Analysis Workflow
- **Model fitting**: Use `curve_fit(logistic_func, years, population, p0=[130e6, 0.04, 1990])` for population forecasting
- **Regression analysis**: Apply OLS with `statsmodels` for correlation analysis, check VIF for multicollinearity
- **Model validation**: Compare AIC/BIC/R² metrics, perform sensitivity analysis and bootstrapping
- **Forecasting**: Generate predictions to 2050 using fitted logistic curves

### Visualization & Reporting
- **Plot generation**: Save figures with `plt.savefig('populations/plot_name.png', dpi=100, bbox_inches='tight')`
- **Vietnamese documentation**: Write all reports and analysis in Vietnamese with proper academic formatting
- **Data validation**: Include model diagnostics, uncertainty estimates, and limitation discussions

## Project-Specific Patterns

### Data Handling Conventions
- **Missing data**: Use `df.interpolate(method='linear')` for time series gaps
- **Outlier detection**: Apply IQR method: `Q1 = df[col].quantile(0.25); Q3 = df[col].quantile(0.75); IQR = Q3 - Q1`
- **Value ranges**: Validate against known bounds (fertility: 1.0-8.0, life expectancy: 30-90, median age: 15-50)
- **File paths**: Reference data relatively (e.g., `'0_rawdata/WPP/WPP2024_Demographic_Indicators_Medium.csv'`)

### Modeling Patterns
- **Logistic growth**: `def logistic_func(t, K, r, t0): return K / (1 + np.exp(-r * (t - t0)))`
- **Population forecasting**: Fit with initial parameters `[130e6, 0.04, 1990]` representing carrying capacity, growth rate, and inflection point
- **Statistical validation**: Always report R² > 0.99 for population models, include confidence intervals
- **Sensitivity analysis**: Test parameter variations of ±10-20% on key assumptions

### Vietnamese Documentation Standards
- **Report structure**: Include executive summary, methodology, results, conclusions, and limitations
- **Academic formatting**: Use proper Vietnamese typography, reference international sources
- **Visualization naming**: Use descriptive Vietnamese names for plot files in `populations/` directory
- **Data citation**: Reference WPP 2024, World Bank indicators, and GSO statistics

## Common Tasks & Examples

### Data Loading Pattern
```python
# Load WPP demographic data
wpp_df = pd.read_csv('0_rawdata/WPP/WPP2024_Demographic_Indicators_Medium.csv')
vietnam_data = wpp_df[wpp_df['Location'] == 'Viet Nam'].copy()

# Rename columns to English standards
column_mapping = {
    'TPopulation1July': 'Population',
    'MedianAgePop': 'Median Age',
    'TFR': 'Fertility Rate',
    'LEx': 'Life Expectancy'
}
vietnam_data = vietnam_data.rename(columns=column_mapping)
```

### Model Fitting Example
```python
from scipy.optimize import curve_fit
import numpy as np

def logistic_func(t, K, r, t0):
    return K / (1 + np.exp(-r * (t - t0)))

# Fit logistic model to population data
years = vietnam_data['Year'].values
population = vietnam_data['Population'].values
popt, pcov = curve_fit(logistic_func, years, population, p0=[130e6, 0.04, 1990])

# Generate forecast
future_years = np.arange(2026, 2051)
forecast = logistic_func(future_years, *popt)
```

### Visualization Pattern
```python
import matplotlib.pyplot as plt
import seaborn as sns

# Set Vietnamese-friendly plotting style
plt.style.use('seaborn-v0_8')
plt.rcParams['font.family'] = 'DejaVu Sans'

# Create population trend plot
fig, ax = plt.subplots(figsize=(12, 8))
ax.plot(vietnam_data['Year'], vietnam_data['Population']/1e6, 'b-', linewidth=2, label='Historical')
ax.plot(future_years, forecast/1e6, 'r--', linewidth=2, label='Forecast')
ax.set_title('Dân số Việt Nam 1955-2050 (triệu người)', fontsize=14, fontweight='bold')
ax.set_xlabel('Năm')
ax.set_ylabel('Dân số (triệu người)')
ax.legend()
ax.grid(True, alpha=0.3)
plt.tight_layout()
plt.savefig('1_Mô hình toán sinh thái/populations/population_forecast.png', dpi=100, bbox_inches='tight')
```

## Quality Standards
- **Statistical rigor**: Include model diagnostics (VIF for multicollinearity, heteroskedasticity tests, R² validation)
- **Data validation**: Cross-reference multiple sources, validate against GSO official statistics
- **Uncertainty quantification**: Implement bootstrap confidence intervals for all forecasts
- **Reproducibility**: Use fixed random seeds for stochastic processes, document all assumptions
- **Vietnamese accuracy**: Ensure proper academic Vietnamese in all reports and documentation

## Key Files to Reference
- `2_Trực quan hóa thông tin/vietnam_consolidated_final_1955_2025.csv`: Consolidated dataset (35 columns, 1955-2025)
- `1_Mô hình toán sinh thái/BaoCaoTongHop_MoHinhToanSinhThai.md`: Main analysis report in Vietnamese
- `2_Trực quan hóa thông tin/BaoCao_ThuThapDuLieu.md`: Data collection methodology documentation
- `1_Mô hình toán sinh thái/populations/`: Directory containing all visualization outputs
- `0_rawdata/WPP/WPP2024_Demographic_Indicators_Medium.csv`: Primary WPP demographic data source</content>
<parameter name="filePath">d:\project\demography-vietnam\.github\copilot-instructions.md