# Financial Fraud Detection System

This project is an end-to-end Machine Learning application designed to analyze and predict the risk of financial fraud based on transaction details (such as transaction type, amount, and sender/receiver balances). It features an analysis pipeline built using Scikit-Learn and an interactive, user-friendly interface powered by **Streamlit** to facilitate live predictions.

##  Project Structure

* **`analysis_model.ipynb`**: Contains the complete exploratory data analysis (EDA), data preprocessing (scaling and encoding), model training, evaluation metrics, and the persistence steps.
* **`fraud_detection_pipeline.pkl`**: The exported Scikit-Learn `Pipeline` object (serialized using `joblib`), encapsulating data preprocessing (`StandardScaler` for numeric inputs, `OneHotEncoder` for categorical categories) and the trained classification model.
* **`fraud_detection.py3`**: The main script for the Streamlit web application that serves the interface for interactive predictions.

---

##  Installation & Setup

To run this project locally, ensure you have **Python 3.8+** installed on your system.

### 1. Clone or Download the Project

Navigate to the directory containing your project files using a terminal or command prompt:

```bash
cd /path/to/fraud-detection-project

```

### 2. Create a Virtual Environment (Recommended)

It is highly recommended to isolate dependencies using a virtual environment:

```bash
# macOS / Linux
python3 -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
venv\Scripts\activate

```

### 3. Install Dependencies

Install all required libraries and packages by executing the following command:

```bash
pip install streamlit pandas numpy scikit-learn joblib matplotlib seaborn notebook

```

---

##  How to Run

### Starting the Streamlit Web Application

To launch the interactive dashboard, run this command in your terminal:

```bash
streamlit run fraud_detection.py3

```

Once initialized, the terminal will display a local address (typically `http://localhost:8501`). If your browser does not open automatically, copy and paste that URL into your browser to view the application.

### Examining the Model Analysis (Optional)

If you wish to explore the data engineering steps, pipeline building, confusion matrices, and metrics (Model Accuracy: ~`94.61%`), launch Jupyter Notebook:

```bash
jupyter notebook

```

Then select and open `analysis_model.ipynb` from the dashboard interface.

---

##  Application Usage & Features

The web interface provides explicit input components for financial transaction details:

1. **Transaction Type:** Choose between `PAYMENT`, `TRANSFER`, `CASH_OUT`, and `CASH_IN`.
2. **Amount:** The total value being transferred.
3. **Old Balance (Sender):** The sender account balance prior to the transaction.
4. **New Balance (Sender):** The sender account balance after the transaction.
5. **Old Balance (Receiver):** The receiver account balance prior to the transaction.
6. **New Balance (Receiver):** The receiver account balance after the transaction.

After adjusting these parameters, click the **"Predict"** button. The app will feed the data straight into the pipeline and instantly indicate whether the transaction is **Legitimate (0)** or carries a **Fraud Risk (1)**.

---

##  Model Metrics

* **Pipeline Integration:** Handles standard numerical transformations alongside categorical structural variables seamlessly without any external alignment necessary.
* **Performance:** The model achieves an overall accuracy score of **94.61%** on testing partitions. Detailed classification configurations can be audited inside the repository notebook.
