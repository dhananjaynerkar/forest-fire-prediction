---
title: Forest Fire Prediction
emoji: 📚
colorFrom: indigo
colorTo: gray
sdk: gradio
sdk_version: 5.25.2
app_file: app.py
pinned: false
license: mit
short_description: Predict forest fire risk using Fire Weather Index (FWI)
---
# Forest Fire Prediction

<div align="center">

[![Hugging Face Spaces](https://img.shields.io/badge/🤗_Spaces-Live_Demo-blue?style=for-the-badge&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAA4AAAAOCAYAAAAfSC3RAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAEQSURBVHgBjZLNTcNAEIXfrJMoPSAkpwNTAaYCSAfugFQAqYBQAe4AXwPkRqiADhAdhBtxsNm3rCWvvAkXRhp5d/bb92dG4I8KrXbrLOWBYAO7fenN3fOj+q/YqM20rvPZvkJViP1kDlrD+wjnmxkxPpBqJQPqFZ0PHn1gHxsnBj6ZEZZRgC+kGrCkX6QpjxT/MAr1OeVGUpCD1jBz0F6USQP2F3vQdwsrt0hKHik+A6hqGa3gKnKDzAA7ogPDGu7VwWbpuECKlK4BUQXx3kRXchqBHYoO67CXyoYz5R2URSoZ9oAXJ0r5DshXwNQkNrK2ZFHAcGIhQvN5cq4UZVHrNHwpZPK7NrGN/NT9SqKL+ALkKyoGlCkYZwAAAABJRU5ErkJggg==)](https://huggingface.co/spaces/dhananjay1509/forest-fire-prediction)
[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org)
[![Gradio](https://img.shields.io/badge/Gradio-5.25.2-FF7C00?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTEyIDJMMiA3djEwbDEwIDUgMTAtNVY3TDEyIDJ6Ii8+PC9zdmc+)](https://gradio.app/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-Latest-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![NumPy](https://img.shields.io/badge/NumPy-Latest-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org)
[![Pandas](https://img.shields.io/badge/Pandas-Latest-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![License](https://img.shields.io/badge/License-MIT-22C55E?style=for-the-badge&logo=opensourceinitiative&logoColor=white)](https://opensource.org/licenses/MIT)

</div>

---

Check out the configuration reference at https://huggingface.co/docs/hub/spaces-config-reference

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Demo](#demo)
- [Installation](#installation)
- [Usage](#usage)
- [Input Parameters](#input-parameters)
- [Risk Levels](#risk-levels)
- [Technical Details](#technical-details)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## 🌟 Overview

This machine learning-based system predicts the Fire Weather Index (FWI) in forest areas using meteorological and environmental factors. It provides real-time risk assessment and recommendations for fire prevention and management.

## ✨ Features

- **Real-time Predictions**: Instant FWI calculations
- **Interactive Interface**: User-friendly web interface with intuitive controls
- **Risk Assessment**: Three-level risk classification system
- **Smart Recommendations**: Contextual advice based on risk levels
- **Input Validation**: Comprehensive parameter validation
- **Visual Feedback**: Color-coded results and clear visual indicators

## 🎮 Demo

Try the live demo on Hugging Face Spaces: [Forest Fire Prediction Demo](https://huggingface.co/spaces/dhananjay1509/forest-fire-prediction)


![Demo Screenshot](demo1.PNG)
![Demo Screenshot](demo2.PNG)
![Demo Screenshot](demo3.PNG)

## 🚀 Installation

### Prerequisites

- Python 3.8 or higher
- pip package manager

### Setup Steps

```bash
# Clone the repository
git clone https://github.com/dhananjaynerkar/forest-fire-prediction.git
cd forest-fire-prediction

# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows

# Install dependencies
pip install -r requirements.txt

# Run the application
python app.py
```

## 💻 Usage

1. Access the web interface at `http://localhost:7861`
2. Input environmental parameters using the sliders
3. Select the region and fire class
4. Click "Predict Fire Weather Index"
5. Review the prediction, risk level, and recommendations

## 📊 Input Parameters

| Parameter         | Range     | Description                             |
| ----------------- | --------- | --------------------------------------- |
| Temperature       | 22-42°C   | Ambient temperature                     |
| Relative Humidity | 21-90%    | Air humidity percentage                 |
| Wind Speed        | 6-29 km/h | Wind velocity                           |
| Rain              | 0-16.8 mm | Rainfall amount                         |
| FFMC              | 28.6-92.5 | Fine Fuel Moisture Code                 |
| DMC               | 1.1-65.9  | Duff Moisture Code                      |
| ISI               | 0-18.5    | Initial Spread Index                    |
| Classes           | 0 or 1    | Fire occurrence (0: No, 1: Yes)         |
| Region            | 0 or 1    | Location (0: Bejaia, 1: Sidi-Bel Abbes) |

## 🎯 Risk Levels

### Low Risk (0-10)

- Regular monitoring recommended
- Standard fire prevention measures
- Suitable for controlled burns

### Moderate Risk (11-20)

- Enhanced monitoring required
- Increased vigilance needed
- Review of fire response procedures

### High Risk (>20)

- Immediate precautions necessary
- Constant monitoring required
- Emergency response team standby

## 🔧 Technical Details

### Model Architecture

- **Algorithm**: Ridge Regression with Cross-Validation (RidgeCV)

  - Selected for its robust performance with continuous target variables
  - Handles multicollinearity in weather-related features
  - Reported checkpoint: R² 0.9843 and MAE 0.5642 on a 61-row holdout; this small-sample result is not a production generalization guarantee.

- **Feature Engineering**:

  - Input features correlation analysis (threshold: 0.85)
  - Removed highly correlated features to prevent multicollinearity
  - Feature scaling using StandardScaler
  - Normalized numerical features to [0,1] range

- **Model Pipeline**:

  1. Input Validation: Range-based checks for all parameters
  2. Feature Preprocessing: StandardScaler transformation
  3. Prediction: Ridge Regression model
  4. Post-processing: Risk level classification and recommendations

- **Performance Metrics**:
  - Cross-validation: 5-fold CV
  - Evaluation metrics: MAE, R² Score
  - Model persistence using pickle serialization

### Technologies Used

- **Backend**: Python, scikit-learn
- **Frontend**: Gradio 5.25.2+
- **Data Processing**: NumPy, Pandas
- **Model Serialization**: Pickle
- **Deployment**: Hugging Face Spaces
- **Version Control**: Git LFS for model files

## 📁 Project Structure

```
forest-fire-prediction/
│
├── app.py                 # Main application file
├── dataset/              # Dataset directory
│   └── Algerian_forest_fires_cleaned_dataset.csv
├── models/               # Model directory
│   ├── ridge.pkl         # Trained model
│   └── scaler.pkl        # Fitted scaler
├── notebooks/            # Jupyter notebooks
│   ├── EDA And FE Algerian Forest Fires.ipynb
│   └── Model Training.ipynb
├── venv/                 # Virtual environment
├── .env                  # Environment variables
├── .env.example          # Environment variables template
├── .gitattributes        # Git LFS configuration
├── .gitignore           # Git ignore rules
├── demo1.PNG             # Demo screenshots
├── demo2.PNG
├── demo3.PNG
├── deploy.py             # Deployment script
└── requirements.txt     # Dependencies
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

## 👥 Authors

- Dhananjay Nerkar - [GitHub](https://github.com/dhananjaynerkar)

## 🙏 Acknowledgments

- [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/547/algerian+forest+fires+dataset) for providing the Algerian Forest Fires Dataset
- The research paper: "Predicting Forest Fire in Algeria using Data Mining Techniques: Case Study of the Decision Tree Algorithm" by Faroudja ABID et al.
- [Hugging Face](https://huggingface.co/) for hosting the demo application
- [Gradio](https://gradio.app/) team for the excellent UI framework
- All contributors and reviewers who helped improve this project

## 📧 Contact

Dhananjay Nerkar - nerkarr.dhananjay@gmail.com
Project Link: [https://github.com/dhananjaynerkar/forest-fire-prediction](https://github.com/dhananjaynerkar/forest-fire-prediction)















