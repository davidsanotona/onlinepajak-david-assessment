# PajakSight: B2B Vendor & Audit Intelligence MVP

PajakSight is an automated AI and machine learning reporting co-pilot designed for CFOs and Heads of Tax. It analyzes inbound B2B tax invoice data to instantly highlight hidden audit risks, chaotic spend patterns, and inefficient vendor relationships.

## Key Architectural Features
* **Dual-Benchmarking:** Evaluates vendor operational efficiency against both historical company baselines (Z-scores) and platform-wide peer medians.
* **Phantom Vendor Detection:** Deploys an Unsupervised ML model (`IsolationForest`) to detect highly anomalous spend volatility and vendor concentration.
* **Audit Risk Monitoring:** Mathematically flags entities deviating >10% from expected VAT baselines.
* **Zero-Hallucination AI:** Uses a local Hugging Face LLM (`flan-t5-small`) locked behind a deterministic prompt to generate plain-English strategic recommendations based *strictly* on factual data inputs.
* **Simulated Deployment:** Implements a strict 8:4 month time-split to train baselines on historical data and evaluate live deployment without temporal data leakage.

## Repository Structure
* `PajakSight_MVP.ipynb`: The main Jupyter Notebook containing the data pipeline, ML scoring engine, LLM integration, and interactive `ipywidgets` dashboard.
* `requirements.txt`: List of Python dependencies required to run the notebook.
* `company_metrics_data.csv`: data used for running the notebook

## How to Run Locally (The MVP won't work on github, you need to run it on your own IDE)

**1. Clone the repository:**
```bash
git clone https://github.com/davidsanotona/onlinepajak-david-assessment.git
cd YOUR_REPO_NAME
```
**2. Install dependencies:**

```bash
pip install -r requirements.txt
```

**3. Launch the Notebook:**
```bash
jupyter notebook PajakSight_MVP.ipynb
```
**4. Interact with the Dashboard:**
Open the notebook and click "Restart & Run All". Scroll to the very bottom to find the interactive UI. Select a Company ID (e.g., C001) and a Live Month (e.g., 2025-09) and click "Run Intelligence".
First-Run Note: The first time you click the run button, the notebook will take a moment to download a lightweight NLP model (google/flan-t5-small) into your local Hugging Face cache. All subsequent runs will execute instantly.