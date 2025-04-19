# 🏦 Bank Marketing Campaign Data Cleaning Project



This project focuses on cleaning and restructuring marketing campaign data from a bank using **Python** to prepare it for use in a PostgreSQL database. The cleaned data will enable easy integration of future campaigns and support data-driven decisions aimed at increasing personal loan uptake.

---

## 📊 Project Overview

Personal loans are a major revenue source for banks. With average interest rates around 10%, even modest borrowing volumes can translate into substantial profits. In this project, we work with a dataset collected during a bank’s marketing campaign designed to promote personal loans.

The raw dataset (`bank_marketing.csv`) contains mixed data types and formats that must be cleaned and split using **Python** into three structured CSV files: `client.csv`, `campaign.csv`, and `economics.csv`. These final outputs conform to strict formatting guidelines for PostgreSQL ingestion and future scalability.

---

## 🧹 Data Cleaning Tasks with Python

The dataset is cleaned using Python’s `pandas` library, applying the following transformations:

### 📁 `client.csv`
| Column         | Type    | Description                        | Cleaning                                           |
|----------------|---------|------------------------------------|----------------------------------------------------|
| `client_id`    | Integer | Client ID                          | —                                                  |
| `age`          | Integer | Client's age                       | —                                                  |
| `job`          | Object  | Job type                           | Replace `.` with `_`                               |
| `marital`      | Object  | Marital status                     | —                                                  |
| `education`    | Object  | Education level                    | Replace `.` with `_`, convert `"unknown"` to `NaN` |
| `credit_default` | Boolean | Credit default status             | `"yes"` → `1`, otherwise `0`                       |
| `mortgage`     | Boolean | Existing housing loan              | `"yes"` → `1`, otherwise `0`                       |

---

### 📁 `campaign.csv`
| Column                   | Type     | Description                          | Cleaning                                                 |
|--------------------------|----------|--------------------------------------|----------------------------------------------------------|
| `client_id`              | Integer  | Client ID                            | —                                                        |
| `number_contacts`        | Integer  | Contacts in current campaign         | —                                                        |
| `contact_duration`       | Integer  | Duration of last contact (sec)       | —                                                        |
| `previous_campaign_contacts` | Integer | Contacts in previous campaign    | —                                                        |
| `previous_outcome`       | Boolean  | Outcome of previous campaign         | `"success"` → `1`, otherwise `0`                         |
| `campaign_outcome`       | Boolean  | Outcome of current campaign          | `"yes"` → `1`, otherwise `0`                             |
| `last_contact_date`      | Date     | Last contact date                    | Combine `day`, `month`, `year=2022` → `"YYYY-MM-DD"`     |

---

### 📁 `economics.csv`
| Column                 | Type   | Description                                 | Cleaning |
|------------------------|--------|---------------------------------------------|----------|
| `client_id`            | Integer| Client ID                                   | —        |
| `cons_price_idx`       | Float  | Consumer Price Index                        | —        |
| `euribor_three_months` | Float  | 3-month Euribor rate                        | —        |

---

## 🐍 Tools & Libraries Used

- Python 🐍
- pandas
- numpy
- datetime

---

## 📂 Input File

- **`bank_marketing.csv`**  
  Raw marketing data to be cleaned and split.

---

## 🧑‍💼 Author

**Abdelrhman Hamdy**  
[LinkedIn Profile](https://www.linkedin.com/in/abdelrahman-hamdii/)
