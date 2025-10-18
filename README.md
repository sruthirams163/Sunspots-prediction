# ☀️ Sunspots Prediction using Machine Learning

This project was created as part of the **Udemy Certification Course** under **Spartificial Innovations Pvt. Ltd.**  
It demonstrates how **machine learning techniques** can be used to analyze **sunspots** — dark magnetic regions on the Sun’s surface — by leveraging **time series data** and **deep learning models**.  
The aim is to showcase how **neural networks** can predict the future activity of sunspots based on historical data.


##  Overview
Sunspots are areas with intense magnetic activity and significantly lower surface temperatures, appearing as dark patches on the Sun’s surface.  
They follow an approximately **11-year cycle of activity**, increasing and decreasing over time.  
This project utilizes **historical sunspot data** to train sequence models like **LSTM (Long Short-Term Memory)** to forecast future solar activity.


##  Theoretical Background

### 1. Sunspot Data and Solar Cycle
- Sunspots are indicators of **solar magnetic activity**.  
- The dataset spans over **two centuries (1749–2021)**, capturing different solar cycles.  
- The data include **monthly mean total sunspot numbers**, reflecting sunspot activity over time.

### 2. Sequence Modeling for Time Series
- Sunspot activity is a **sequential time series**, ideal for models that remember past information, such as **Recurrent Neural Networks (RNN)**, **LSTM**, and **GRU**.  
- **LSTM** is chosen for its ability to retain **long-term dependencies** and overcome the **vanishing gradient problem** inherent in vanilla RNNs.

### 3. Model Architecture
- The model uses **Conv1D layers** for smoother feature extraction from raw series.  
- Followed by **stacked LSTM layers** to learn temporal dependencies, and **Dense layers** for final prediction output.  
- The model predicts **monthly sunspot activity**, which can assist in understanding solar behavior.



##  Computational Approach

### 1. Data Handling & Preprocessing
- Data imported from the **CSV file** containing monthly sunspot numbers.  
- The data range covers **1749 to 2021**, with no missing values.  
- Visualization highlights the approximately **11-year cycle**, including the first cycle (around 1749) and the current cycle (started 2019).

### 2. Creating Sequences for LSTM
- Data transformed into **sliding windows** of fixed size (e.g., 60 months) to train the model on sequences.  
- A custom function generates datasets of **windowed sequences** with a batch size for training.

### 3. Building the Long Short-Term Memory (LSTM) Model
- The model includes **Conv1D layers** for feature extraction, followed by **LSTM layers** to learn temporal dependencies.  
- A **Huber loss function** is used for its robustness to outliers in data.  
- The model training involves tuning the **learning rate** using a **learning rate scheduler** to find the optimal value.

### 4. Model Training and Validation
- The dataset is split into **training and validation sets (90% training)**.  
- The training process involves minimizing the **Huber loss** with the **SGD optimizer**.  
- After training, the model’s performance is visualized through **loss curves**.

### 5. Forecasting Future Sunspots
- The trained model predicts **future sunspot activity** based on recent data.  
- The forecast helps visualize the **upcoming solar cycle activity**.


##  Libraries Used
- **Matplotlib & Seaborn** — For data visualization and plotting sunspot cycles.  
- **Pandas & NumPy** — For data processing and numerical operations.  
- **TensorFlow & Keras** — For building and training the deep learning model.  
- **Warnings** — To suppress unnecessary warnings during execution.


## Results and Observations
- The model learns the approximate **11-year sunspot cycle** effectively.  
- Visualizations show the **predicted future cycle** and the **historical activity**.  
- The model's robustness is improved by using **Huber loss** and **adaptive learning rate** methods.  
- Final forecasts highlight **solar activity patterns**, which can be useful for **space weather prediction**.


##  Conclusion
This project demonstrates the power of **sequence models** like **LSTM** in analyzing and forecasting complex time series data such as **sunspots**.  
Understanding the **solar cycle** through AI helps in better **space weather prediction**, which impacts **satellite communication** and **space missions**.
