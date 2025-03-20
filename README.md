# Formula-1-Race-Prediction
Predicting Formula 1 race results using machine learning

## Overview
This project aims to predict Formula 1 race standings using:
- **Qualifying Performance**
- **Past Race Performance**
- **Starting Grid Position**

These factors are used to estimate the overall race time for the 2025 Australian Grand Prix, helping predict final standings. This model is developed using **Python, FastF1 API, and Scikit-Learn**, focusing on predicting race lap times.

---

## Data Collection (FastF1 API)
We extracted historical race and qualifying data from **2024** to serve as the training dataset. The **FastF1 API** provided:
- **Lap times** for all drivers in the 2024 Australian GP
- **Grid positions** for all drivers in 2024
- **Qualifying times** for the 2025 Australian GP (simulated for model testing)

---

## Feature Engineering
To predict 2025 lap times, we used:
- **2024 Lap Times** – Provides historical context for each driver’s race pace.
- **2025 Qualifying Times** – Acts as an initial performance indicator.
- **Grid Position** – Helps capture race start advantage and overtaking difficulty.

Other potential race-day factors like **fuel loads, pit strategy, and weather conditions** were **not included** in this version but would improve future iterations.

---

## Model Selection
The **Gradient Boosting Regressor** from Scikit-Learn was chosen because:
- It is well-suited for **structured tabular data** with **non-linear dependencies**.
- It can capture **complex relationships** between qualifying performance and race pace.
- It is **robust to small datasets**, which is critical given the limited number of F1 races per season.

---

## Model Evaluation
The **Mean Absolute Error (MAE)** of the model is **3.47 seconds**, meaning the average deviation per lap is 3.47 seconds from actual lap times. Since milliseconds matter in F1, improving accuracy is crucial.

---

## Key Challenges & Limitations
- **Limited Data for New Drivers** – If a driver did not compete in 2024, the model has no prior lap time data, leading to uncertainty.
- **Model Error (MAE: 3.47 sec)** – While reasonable for a proof of concept, milliseconds can decide race winners.
- **Missing Race-Day Variables** – Weather, pit strategy, tire degradation, and race pace fluctuations are critical but were not included in this version.

---

## Future Improvements
To enhance accuracy, the following variables could be incorporated:
- **Tire Strategy** – Soft tires are faster but degrade quickly, while hard tires last longer.
- **Weather & Track Conditions** – Rain introduces unpredictability, and grip levels change throughout a race.
- **Race Pace Trends** – Some cars gain speed over long stints, while others degrade quickly.
- **Pit-Stop Strategy** – Undercuts, overcuts, and safety car interventions play a role in real race outcomes.
- **Overtaking Difficulty Per Track** – Not every circuit is Monaco, but overtaking varies drastically by track.

---

## How to Use This Repository
### 1️⃣ Clone the Repository
```bash
git clone https://github.com/navya-singhal/formula-1-race-prediction.git
cd formula-1-race-prediction
```

### 2️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```
*(If you don't have a `requirements.txt`, I can generate one for you.)*

### 3️⃣ Run the Notebook
If using Jupyter Notebook:
```bash
jupyter notebook
```
Open `Formula_1_2025_Prediction.ipynb` and execute the cells.

If using **Google Colab**, upload the notebook and run it directly.

### 4️⃣ Modify & Experiment
- Adjust model parameters in `Formula_1_2025_Prediction.ipynb`
- Try adding new **features** like weather, tire degradation, or pit-stop strategy.
- Run different ML models (Random Forest, XGBoost, etc.) for comparison.

### 5️⃣ Contribute
Found an issue or have an improvement idea? Open a **Pull Request** or raise an **Issue** in the repo!

---

## Acknowledgments
Special thanks to **Mariana Antaya** for the inspiration behind this project! This model is a **proof of concept**, and I plan to **keep improving it as the F1 season progresses**. 🚀

