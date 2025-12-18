# Database Schema Design
## Star Schema for Fraud Analytics

---

## Fact Table

### fact_transactions
| Column Name | Description |
|------------|------------|
| transaction_id | Unique transaction identifier |
| user_id | Reference to user |
| merchant_id | Reference to merchant |
| device_id | Reference to device |
| location_id | Reference to location |
| time_id | Reference to time dimension |
| amount | Transaction amount |
| fraud_score | ML-generated fraud score |
| is_fraud | Fraud decision |

---

## Dimension Tables

### dim_user
| Column | Description |
|------|------------|
| user_id | Primary key |
| account_age | Age of user account |
| risk_profile | Risk category |

### dim_merchant
| Column | Description |
|------|------------|
| merchant_id | Primary key |
| category | Merchant category |
| country | Merchant country |

### dim_device
| Column | Description |
|------|------------|
| device_id | Primary key |
| device_type | Mobile/Desktop |
| os | Operating system |

### dim_location
| Column | Description |
|------|------------|
| location_id | Primary key |
| city | City |
| country | Country |

### dim_time
| Column | Description |
|------|------------|
| time_id | Primary key |
| date | Date |
| hour | Hour |
| day | Day |
| month | Month |
| year | Year |

---

## Design Rationale
A star schema is used to optimize analytical queries, improve performance, and simplify dashboard reporting.
