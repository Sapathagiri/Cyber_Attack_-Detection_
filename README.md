# Cyber Attack Detection System

This project implements a machine learning-based Intrusion Detection System (IDS) that can identify and classify different types of cyber attacks using network traffic data.

## Overview

The system uses two machine learning algorithms:
1. Random Forest with Principal Component Analysis (PCA-RF)
2. Support Vector Machine (SVM)

Both models are trained on network traffic data to detect various types of cyber attacks including:
- Back attacks
- Buffer overflow
- Guess password attempts
- Port scanning
- Network probing
- And more...

## Requirements

The project requires the following Python packages:
```
pandas
scikit-learn
imbalanced-learn
matplotlib
scipy
```

You can install all requirements using:
```bash
pip install -r requirements.txt
```

## Dataset

The project uses the `cybermg.csv` dataset which contains network traffic data with the following features:
- Protocol type
- Service
- Flag
- Duration
- Source and destination bytes
- Various network statistics
- Attack class labels

## Project Structure

```
CyberAttack/
├── IntrusionDetection.py    # Main detection script
├── cybermg.csv             # Dataset file
├── requirements.txt        # Project dependencies
└── README.md              # This file
```

## How It Works

The detection system works in the following steps:

1. **Data Loading**: Loads the network traffic dataset
2. **Preprocessing**: 
   - Converts categorical features to numerical using Label Encoding
   - Handles imbalanced data using SMOTE (Synthetic Minority Oversampling Technique)
3. **Feature Selection**: 
   - Applies Principal Component Analysis (PCA) for dimensionality reduction
4. **Model Training and Evaluation**:
   - Trains Random Forest and SVM models
   - Evaluates model performance using accuracy metrics
   - Generates comparison plots

## Running the System

To run the intrusion detection system:

1. Make sure all requirements are installed:
```bash
pip install -r requirements.txt
```

2. Run the main script:
```bash
python IntrusionDetection.py
```

The script will:
- Load and preprocess the data
- Train both models
- Display accuracy results
- Show a comparison plot

## Results

In our tests, the models achieved the following accuracy:
- PCA-RF: ~86.4% accuracy
- SVM: ~51.6% accuracy

The Random Forest classifier with PCA shows significantly better performance in detecting cyber attacks compared to the SVM approach.

## Future Improvements

Potential areas for enhancement:
1. Feature engineering to improve detection accuracy
2. Implementation of additional machine learning algorithms
3. Real-time detection capabilities
4. Enhanced visualization of results
5. Support for additional types of cyber attacks

## Contributing

Feel free to contribute to this project by:
1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## Commands Reference

Here are the common commands you'll need to work with this system:

### Setup Commands

```bash
# Clone the repository (if using git)
git clone <repository-url>
cd CyberAttack

# Create a virtual environment (recommended)
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On Unix or MacOS:
source venv/bin/activate

# Install requirements
pip install -r requirements.txt
```

### Running the System

```bash
# Run the main detection script
python IntrusionDetection.py

# To run with specific Python version (if multiple installed)
python3 IntrusionDetection.py
```

### Development Commands

```bash
# Check Python version
python --version

# List installed packages
pip list

# Update pip
python -m pip install --upgrade pip

# Install a new package and add to requirements
pip install <package-name>
pip freeze > requirements.txt
```

### Troubleshooting Commands

```bash
# Check if required packages are installed
pip show pandas
pip show scikit-learn
pip show imbalanced-learn
pip show matplotlib
pip show scipy

# Verify dataset exists
dir cybermg.csv  # On Windows
ls cybermg.csv   # On Unix/MacOS

# Check Python path
python -c "import sys; print(sys.path)"
