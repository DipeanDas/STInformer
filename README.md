# Spatio-Temporal Informer(ST-Informer) Model
This repository contains the implementation of a **Scalable Informer-based deep learning architecture** for **water quality forecasting**. The model is trained and tested on **multivariate water quality data** collected from various locations of the **16 major rivers Indian Himalayan Rivers**. Although demonstrated on the Indian Rivers dataset, the architecture is **generalizable**, **customizable** and can be applied to **other river systems or water quality monitoring datasets**.<br>
An interactive **Flask-based web interface** is also developed to deploy the trained model for near-accurate prediction and visualization.

## ST Informer Architecture
<img width="852" height="327" alt="ST_Informer_architecture" src="https://github.com/user-attachments/assets/af97db9a-8256-4745-8044-8f1fff763ff4" />


## 📊Training Dataset Overview:
 - Source: Indian Himalayan River water quality dataset.
 - Time Period: 2022-2024
 - Locations Count: 44
 - Water Quality parameters count: 23[BOD, COD, DO, pH, TDS,TC,FC,Nitrate and others]
 - Contextual parameters count: 3[Location. Year, Month]
 - Primary Target Parameter: Biochemical Oxygen Demand (BOD).  
 - Other Target Parameters:Chemical Oxygen Demand(COD),Dissolved Oxygen(DO) and Total Dissolved Solid(TDS)

## 📂 Project Structure
The model codebase is structured in the following way:
```
Spatio-Temporal_Informer_Model/
│
├── exp/
│ └── exp_informer.py # Experiment pipeline: training, validation, testing
│
├── models/
│ ├── informer.py # Core Informer model integration
│ ├── encoder.py # Encoder layers (self-attention, conv, feedforward)
│ ├── decoder.py # Decoder layers (masked + cross attention)
│ ├── embed.py # Embedding layers (temporal, positional, data embedding)
│ └── attn.py # ProbSparse & Full Attention mechanisms
│
├── utils/
│ ├── tools.py # Metrics (MSE, MAE, R², PLCC, SRCC and KRCC)
│ ├── data_loader.py # Data preprocessing + DataLoader for train/val/test
│ └── custom_data_process.py # CSV preprocessing (scaling, feature extraction)
│
├── score_metrics/
│ └── metrics.txt # Saved test scores for BOD,COD,DO,TDS
│
├── static/
│ └── styles.css # CSS styling for Flask web app
│
├── templates/
│ ├── index.html # Home page template
│ └── predict.html # Prediction page template
│
├── config.py # Configurations (Model  training and testing parameter value setup)
├── main.py # Entry point: Training process initiator
├── pred_app.py # Prediction pipeline/system logic
├── app.py # Flask application initiator
├── requirements.txt # Python libraries and dependencies
└── README.md # Project documentation file
```
## ⚙️ Dependencies

This project was developed and tested with the following dependencies:
```
- Python 3.10  
- torch >= 1.10.0  
- numpy >= 1.21.0  
- pandas >= 1.3.0  
- scikit-learn >= 1.0.0  
- matplotlib >= 3.4.0  
- joblib >= 1.0.0  
- openpyxl >= 3.0.0  
- python-dateutil >= 2.8.0
- scipy >= 1.7.0  
- flask >= 2.0.0  
```

## ⚙️ Installation
Clone the repository and install the required dependencies:
```
git clone https://github.com/DipeanDas/Spatio_Temporal_Informer_for_Water_Quality_Prediction.git
cd Spatio_Temporal_Informer_for_Water_Quality_Prediction
pip install -r requirements.txt 
```
### Notes and Precautions
While the ST-Informer architecture is scalable and adaptable aspects like hyperparameters, sequence lengths, and preprocessing steps should be tuned according to the specific dataset and forecasting objective. For different data structures, temporal resolutions, or experimental setups, appropriate modifications to the data loading and preprocessing pipeline may be required to ensure correct training and evaluation.

## 👨‍💻 Contributors

**Dipean Dasgupta** (Department of CSE, IIIT Vadodara, India)<br>
**Bishnu Prasad Sahoo** (Forest Ecology and Climate Change Division, Forest Research Institute, Dehradun, India)<br>
**Pramit Mazumdar** (Department of CSE, IIIT Vadodara, India)<br>

