## Lead Scoring System

## Overview

This project builds a rule-based lead scoring system that assigns a score (0–100) to companies based on business-relevant features.

The system evaluates leads using:

* Company size
* Funding amount
* Industry relevance
* Contact seniority

---

## Tech Stack

* Python
* Pandas
* FastAPI

---

## Project Structure

```
lead_scoring_project/
│
├── data/
│   └── raw_data.xlsx
│
├── app/
│   ├── main.py
│   ├── scoring.py
│   ├── preprocess.py
│   └── utils.py
│
├── run.py
├── requirements.txt
└── README.md
```

---

## ▶️ How to Run

### 1. Install dependencies

```
pip install -r requirements.txt
```

### 2. Run preprocessing

```
python app/preprocess.py
```

### 3. Test scoring

```
python run.py
```

### 4. Run API

```
python -m uvicorn app.main:app --reload
```

Open in browser:

```
http://127.0.0.1:8000/docs
```

---

## 🧠 Scoring Logic

The scoring system assigns points based on:

| Feature      | Logic                               |
| ------------ | ----------------------------------- |
| Company Size | Larger companies get higher score   |
| Funding      | Higher funding → higher score       |
| Seniority    | Decision-makers score higher        |
| Industry     | Tech/software companies prioritized |

---

## Why Rule-Based?

* No labeled data available
* Easier to interpret
* Faster to implement
* Business-friendly explanation

---

## Data Processing

* Removed irrelevant columns
* Handled missing values
* Converted:

  * "1000+" → numeric
  * "$991M" → numeric
* Created new features:

  * employees_numeric
  * funding_numeric

---

## Future Improvements

* Add revenue conversion
* Train ML model (if labeled data available)
* Add batch scoring endpoint
* Integrate with CRM systems
* Deploy on cloud (AWS/GCP)

---

## Example Output

```
Score: 60
Explanation: ['Large company', 'Highly funded', 'Senior leadership']
```

---

## Author

Sanidhya Bhagat
