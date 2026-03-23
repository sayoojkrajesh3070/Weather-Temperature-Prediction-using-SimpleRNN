# Weather Temperature Prediction using SimpleRNN

## 🎯 Objective
The goal of this project is to design, implement, and evaluate a Recurrent Neural Network (RNN) using the `SimpleRNN` architecture to forecast the next day’s temperature based on historical weather data.

## 📊 Dataset
The project uses the **Daily Weather Dataset** (Weather History). Key features used for prediction include:
- **Temperature (C)** (Target Variable)
- **Humidity**
- **Wind Speed (km/h)**

## 🛠️ Data Preprocessing
1. **Resampling:** Converted hourly data into daily averages to reduce noise and focus on daily trends.
2. **Missing Values:** Handled gaps using forward-filling (`ffill`) to maintain time-series continuity.
3. **Scaling:** Normalized all features using `MinMaxScaler` (0 to 1) to ensure stable RNN training.
4. **Windowing:** Created input sequences using a **7-day sliding window** to predict the temperature of the 8th day.

## 🧠 Model Architecture
The model was built using TensorFlow/Keras:
- **SimpleRNN Layer:** 64 units with `tanh` activation.
- **Dropout Layer:** 0.2 rate to prevent overfitting.
- **Dense Layer:** 32 units with `relu` activation.
- **Output Layer:** 1 unit with linear activation for regression.

**Compilation Settings:**
- **Optimizer:** Adam
- **Loss Function:** Mean Squared Error (MSE)
- **Metric:** Mean Absolute Error (MAE)

## 📈 Results
The model was trained for 50 epochs with a batch size of 32. 
- **RMSE:** [Insert your value here, e.g., 2.45°C]
- **R2 Score:** [Insert your value here, e.g., 0.91]

## 🔮 Future Forecasting
The model successfully performs a **recursive 7-day forecast**, using its own previous predictions to estimate the temperature for the upcoming week.
