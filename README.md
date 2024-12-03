# Predictive Analyzer Toolkit

A Python application that analyzes flat data files and runs different predictive modeling tools to help choose the most appropriate model.

## Features

- Supports multiple file formats (CSV, Excel, JSON, TXT)
- Automated data preprocessing and feature engineering
- Multiple predictive modeling algorithms
- Comprehensive model evaluation metrics
- Report generation capabilities

## Project Structure

```
predictive_analyzer/
├── data/
├── src/
│   ├── data_loader/
│   ├── preprocessor/
│   ├── models/
│   ├── evaluation/
│   ├── reporting/
│   └── utils/
├── tests/
├── docs/
├── examples/
└── config/
```

## Requirements

- pandas
- numpy
- scikit-learn
- xgboost
- lightgbm
- streamlit
- shap
- matplotlib
- seaborn
- openpyxl
- reportlab

## Installation

1. Clone the repository:
```bash
git clone https://github.com/fluispereira/predictive-analyzer-toolkit.git
cd predictive-analyzer-toolkit
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

```python
from predictive_analyzer import DataLoader, Preprocessor, ModelManager, Reporter

# Initialize components
data_loader = DataLoader()
preprocessor = Preprocessor()
model_manager = ModelManager()
reporter = Reporter()

# Load and prepare data
df = data_loader.load_file("example_data.csv")
data_summary = data_loader.get_data_summary(df)

# Preprocess data
X, y = preprocessor.preprocess_data(df, target_column="target")

# Train and evaluate models
model_manager.train_all_models(X, y)

# Generate report
report = reporter.generate_comparison_report(model_manager.results)
reporter.save_report_pdf(report, "model_comparison_report.pdf")
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.