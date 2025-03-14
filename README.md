
# Cricket Forecast - Predicting Cricket Match Outcomes

---

#### **Introduction**

This project predicts cricket match outcomes using pre-match conditions and players' performance data. It employs machine learning techniques to analyze One Day International (ODI) and Twenty20 (T20) matches, focusing on factors such as toss decisions, pitch conditions, home advantage, and player statistics. Two models are implemented:
- **Model 1**: Predicts the winning team based on pre-match conditions.
- **Model 2**: Evaluates player performance metrics to forecast team performance.

---

#### **Features**
- **Pre-match Analysis**: Factors such as toss outcome, pitch condition, and home advantage.
- **Player Performance**: Metrics like batting average, bowling economy, and strike rates are analyzed.
- **Machine Learning Models**:
  - **Random Forest Classifier**: Used for predicting match outcomes based on pre-match conditions.
  - **Random Forest Regressor**: Used for analyzing player performance metrics.

---

#### **System Architecture**

The system consists of a **3-tier architecture**:
1. **User Interface (GUI)**: Built using Python's `tkinter`, it collects inputs for pre-match conditions and player statistics.
2. **Server Tier**: Hosts the main business logic for processing inputs, running models, and predicting results.
3. **Database Tier**: Stores the pre-trained models and datasets in pickle format for efficient retrieval.

![image](https://github.com/user-attachments/assets/e2078632-cf6d-40f7-bc5f-31a44fbaccc9)


---

#### **Dataset**

Data was sourced from Kaggle and includes:
1. **Pre-match Conditions**:
   - Team names, toss decision, ground location, home advantage, and pitch condition.
2. **Player Statistics**:
   - Batting data: Runs, strike rate, average.
   - Bowling data: Wickets, economy, average.

---

#### **Preprocessing**

- **Null Handling**: Removes records with missing or irrelevant data.
- **Label Encoding**: Encodes categorical variables like teams and pitch conditions.
- **Normalization**: Min-Max scaling for features like runs, strike rates, and bowling metrics.

---

#### **Models**

1. **Model 1: Pre-match Conditions**
   - Input: Team names, toss outcome, home advantage, and pitch type.
   - Output: Predicted winner.
   - Algorithm: Random Forest Classifier (63% accuracy after hyperparameter tuning).

2. **Model 2: Player Performance**
   - Input: Batting and bowling statistics.
   - Output: Predicted team performance scores.
   - Algorithm: Random Forest Regressor (R² scores: 97% for ODIs, 98% for T20s).

---

#### **Equations**

- **Bowling Performance Score**:
  ```
  Bowl_score = 0.3 * (normalized_wickets) + 0.3 * (normalized_avg) + 0.4 * (normalized_economy)
  ```
- **Team Score Calculation**:
  - Batting pitch:
    ```
    Total_score = 0.6 * (team_bat_score) + 0.4 * (team_bowl_score)
    ```
  - Bowling pitch:
    ```
    Total_score = 0.4 * (team_bat_score) + 0.6 * (team_bowl_score)
    ```
  - Balanced pitch:
    ```
    Total_score = 0.5 * (team_bat_score) + 0.5 * (team_bowl_score)
    ```

---

#### **Installation**

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd cricket-forecast
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the GUI:
   ```bash
   python main.py
   ```

---

#### **Usage**

1. **GUI Input**:
   - Choose the match type (ODI or T20).
   - Enter pre-match conditions (teams, toss, pitch condition).
   - Enter players' statistics for both teams.
   
2. **Prediction Output**:
   - Displays the predicted winning team and percentage scores based on batting and bowling metrics.

---

#### **Results**

- **Model 1**:
  - Accuracy: 63%
  - Precision: 62%
  - Recall: 63%
  - F1-Score: 60%
- **Model 2**:
  - R² Score: 97% (ODI), 98% (T20)
  - Low Mean Squared Error (MSE).

---

#### **Future Enhancements**

1. Include additional covariates like weather conditions and player performance on specific grounds.
2. Implement advanced deep learning models for increased accuracy.
3. Support Test matches and other cricket formats.

---

#### **References**

- Kaggle datasets for cricket statistics.
- Research papers and studies on cricket analytics and machine learning applications.

---

#### GUI Interface

![image](https://github.com/user-attachments/assets/09ccf13d-3cde-409c-befe-1ea7ad7a0e74)


For more details, refer to the link http://dx.doi.org/10.1007/978-3-031-69986-3_27
