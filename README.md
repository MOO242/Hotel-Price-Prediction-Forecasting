# 🏨 Hotel Price Prediction & Forecasting

## 🎯 Project Overview

The goal of this project is to build a robust machine learning pipeline to predict the **Average Daily Rate (ADR)** and forecast booking demand. In the competitive hospitality landscape, accurate price prediction allows for optimized **Revenue Management** and better resource allocation.

## 🔍 Part 1: The Data Audit

Before building models, I conducted a deep-dive audit of the raw dataset (119k+ bookings). A "doer" doesn't ignore the mess; they analyze it. I identified significant "holes" in the data that required strategic handling:

| Column | Missing Values | Industry Interpretation |
| --- | --- | --- |
| **`company`** | 112,593 | Represents private/non-corporate bookings. |
| **`agent`** | 16,340 | Potential "Direct" bookings (no 3rd party agency). |
| **`country`** | 488 | Incomplete guest profile data. |
| **`children`** | 4 | Likely a data entry omission. |

## 💡 Domain-Driven Logic (Business Decisions)

A common mistake is to treat all "null" values as errors and delete them. In this project, I applied **Hospitality Domain Logic** to ensure the dataset remained representative of real-world revenue:

* **The "Direct Booking" Hypothesis:** I identified that missing values in the `agent` and `company` columns were not random. In hospitality, these typically represent **Direct-to-Hotel** bookings.
* **Preserving Profitability:** Deleting these 112k+ rows would have removed the hotel's most profitable customer segment (those not paying commission to 3rd party agents).
* **Action taken:** I imputed these values with `0` to categorize them as "Direct," preserving the integrity of the forecasting model.

## 🛠️ Tech Stack

* **Language:** Python
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn
* **Focus:** Data Auditing, Imputation, Revenue Management

---
