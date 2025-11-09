# AI Coding Assistant Instructions for Vietnamese Demography Analysis Project

## Project Overview
This is a Vietnamese demography research project analyzing population trends from 1955-2050 using mathematical ecological models. The project focuses on demographic transition, aging population, urbanization impacts, and population forecasting using statistical models.

## Architecture & Data Flow
- **0_rawdata/**: Raw datasets from international organizations (World Bank, IMF, FAO, UNDP, UNCTAD)
- **1_Mô hình toán sinh thái/**: Jupyter notebooks for statistical modeling and analysis
- **2_Trực quan hóa thông tin/**: Consolidated datasets and visualization outputs

Data flows from raw sources → consolidation → statistical analysis → forecasting models → visualizations/reports.

## Key Technologies & Libraries
- **Python ecosystem**: pandas, numpy, matplotlib, seaborn, scipy, statsmodels, sklearn
- **Modeling approaches**: Logistic growth models, OLS regression, ARIMA time series, sensitivity analysis
- **Data formats**: CSV files with extensive demographic indicators (population, median age, fertility rate, urbanization, GDP, HDI, etc.)

## Development Workflow
- **Analysis**: Use Jupyter notebooks in `1_Mô hình toán sinh thái/` for exploratory data analysis
- **Data processing**: Load CSVs with pandas, handle missing values via linear interpolation
- **Modeling**: Fit logistic curves for population forecasting, perform OLS regression for correlations
- **Validation**: Compare models using AIC/BIC/R² metrics, conduct sensitivity analysis and bootstrapping
- **Visualization**: Generate plots with matplotlib/seaborn, save to `populations/` subdirectories
- **Reporting**: Create Vietnamese-language reports in Markdown format

## Project-Specific Patterns
- **Language**: Reports and documentation in Vietnamese (Tiếng Việt)
- **Data cleaning**: Convert percentage strings to floats, interpolate missing values
- **Statistical rigor**: Always include model diagnostics (VIF for multicollinearity, heteroskedasticity tests)
- **Forecasting**: Use logistic models for saturation-limited growth, ARIMA for time series patterns
- **Uncertainty**: Implement bootstrap confidence intervals for predictions
- **File paths**: Reference data files relative to notebook location (e.g., `'raw/vietnam.csv'`)

## Common Tasks
- **Data loading**: `df = pd.read_csv('path/to/data.csv', encoding='utf-8')`
- **Logistic fitting**: `popt, _ = curve_fit(logistic_func, years, population, p0=[130e6, 0.04, 1990])`
- **Model comparison**: Evaluate using AIC/BIC scores and R² values
- **Visualization**: `plt.savefig('output/path/plot.png', dpi=100, bbox_inches='tight')`

## Quality Standards
- Use statistical best practices: check for multicollinearity, heteroskedasticity, outliers
- Validate models with cross-validation or holdout sets where applicable
- Document assumptions and limitations in Vietnamese reports
- Ensure reproducible results with fixed random seeds for stochastic processes

## Key Files to Reference
- `1_Mô hình toán sinh thái/BaoCaoCaiThien_Vietnam_Population.ipynb`: Main analysis notebook
- `2_Trực quan hóa thông tin/vietnam_consolidated_final_1955_2025.csv`: Consolidated dataset
- `1_Mô hình toán sinh thái/BaoCaoTongHop_MoHinhToanSinhThai.md`: Comprehensive report</content>
<parameter name="filePath">d:\project\demography-vietnam\.github\copilot-instructions.md