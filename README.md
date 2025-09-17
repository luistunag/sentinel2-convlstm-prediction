Sentinel-2 ConvLSTM Prediction

📌 Project Overview

This project explores the spatiotemporal prediction of satellite indices using Convolutional LSTM (ConvLSTM) networks.
The case study focuses on Sentinel-2 imagery for the department of Quetzaltenango, Guatemala, with data sampled quarterly (Q1–Q4) to capture seasonal vegetation dynamics.

The work was developed as the final project for the course Statistical Learning II.

⸻

🛰️ Data

	•	Source: Sentinel-2 imagery (ESA Copernicus Open Access Hub).
	•	Temporal resolution: Quarterly composites (Q1, Q2, Q3, Q4).
	•	Variables:
	•	NDVI (Normalized Difference Vegetation Index)
	•	NDWI (Normalized Difference Water Index)
	•	SWIR (Short-Wave Infrared)
	•	False Color composites
	•	Moisture Index
	•	Scene Classification Map

All datasets were preprocessed, downsampled, and normalized for model training.

⸻

🔍 Exploratory Analysis

	•	Visualization of each index across different quarters.
	•	Seasonal averages (NDVI, NDWI).
	•	Temporal trends (annual means of NDVI, NDWI, SWIR, and Moisture Index).
	•	Correlation analysis between indices.
	•	Global spatial averages to identify overall patterns.

⸻

🤖 Modeling

	•	Architecture: ConvLSTM with multiple layers and regularization.
	•	Sequence length: 4 timesteps (quarters), equivalent to one year.
	•	Target: Predict the next quarter’s full image for a selected variable.
	•	Hyperparameter tuning: Implemented with Keras Tuner (filters, kernel sizes, dropout rates, learning rate).
	•	Loss function: Combination of Mean Squared Error and Huber loss.

⸻

📈 Results

	•	ConvLSTM captured seasonal vegetation patterns and produced visually consistent predictions.
	•	Predicted NDVI and NDWI maps showed good alignment with ground truth.
	•	Scene classification proved more challenging due to categorical structure, but the pipeline demonstrated flexibility.

⸻

📊 Repository Structure

```
sentinel2-convlstm-prediction/
│── README.md
│── requirements.txt
│
├── notebooks/
│   └── sentinel2_convlstm_quetzaltenango.ipynb
│
├── reports/
│   ├── html/        # rendered notebook
│   ├── figures/     # plots and maps
│   └── results.md   # key findings
│
└── data/
    └── README.md    # instructions for downloading Sentinel-2 data
```

⸻

⚙️ Requirements

See requirements.txt for main dependencies:

	•	tensorflow, keras-tuner
	•	numpy, pandas, matplotlib, seaborn
	•	rasterio, opencv-python
	•	scikit-learn

⸻

📚 References

	•	Shi et al. (2015). Convolutional LSTM Network: A Machine Learning Approach for Precipitation Nowcasting.
	•	Sentinel-2 ESA documentation.
	•	Statistical Learning II course material.

⸻

✍️ Author: Luis Tun
Data Scientist
