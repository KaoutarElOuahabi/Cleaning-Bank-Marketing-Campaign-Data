# :moneybag: Cleaning-Bank-Marketing-Campaign-Data
![Piggy Bank](bank_marketing.webp)

---

## :project: **Project: Data Cleaning for Bank Marketing Campaign**

This project involves cleaning and reformatting data collected from a bank marketing campaign aimed at targeting customers for personal loans. The cleaned data will be prepared for import into a PostgreSQL database and will be used for future marketing campaigns.

> **Note**: This is part of a **Datacamp Data Engineering project**.

---

### :question: **Problem Overview**

Personal loans are a major revenue stream for banks. For example, in September 2022 alone, UK consumers borrowed around **£1.5 billion** ([source](https://www.ukfinance.org.uk/system/files/2022-12/Household%20Finance%20Review%202022%20Q3-%20Final.pdf)), generating an estimated **£300 million in interest** over two years. The typical interest rate of a two-year loan in the United Kingdom is around **10%** ([source](https://www.experian.com/blogs/ask-experian/whats-a-good-interest-rate-for-a-personal-loan/)).

The goal of this project is to clean and structure the data collected by the bank during a marketing campaign aimed at encouraging customers to take out personal loans. The cleaned data will be used to set up a PostgreSQL database that will allow easy import of future campaign data.

---

### :file_folder: **Files Overview**

#### **Input File:**
- `bank_marketing.csv`: Raw data collected from the campaign.

#### **Final Cleaned Files:**

1. **client.csv**
   - `client_id` (integer): Client ID (No cleaning needed)
   - `age` (integer): Client's age in years (No cleaning needed)
   - `job` (object): Client's type of job (Change "." to "_")
   - `marital` (object): Client's marital status (No cleaning needed)
   - `education` (object): Client's education level (Change "." to "_" and "unknown" to np.NaN)
   - `credit_default` (bool): Whether the client has a defaulted credit (1 for "yes", 0 for "no")
   - `mortgage` (bool): Whether the client has a mortgage (1 for "yes", 0 for "no")

2. **campaign.csv**
   - `client_id` (integer): Client ID (No cleaning needed)
   - `number_contacts` (integer): Number of contacts in the current campaign (No cleaning needed)
   - `contact_duration` (integer): Duration of the last contact in seconds (No cleaning needed)
   - `previous_campaign_contacts` (integer): Number of contacts in the previous campaign (No cleaning needed)
   - `previous_outcome` (bool): Outcome of the previous campaign (1 for "success", 0 for "failure")
   - `campaign_outcome` (bool): Outcome of the current campaign (1 for "yes", 0 for "no")
   - `last_contact_date` (datetime): Last date of contact (formatted as "YYYY-MM-DD" using a combination of day, month, and a newly created year column set to 2022)

3. **economics.csv**
   - `client_id` (integer): Client ID (No cleaning needed)
   - `cons_price_idx` (float): Consumer price index (monthly indicator)
   - `euribor_three_months` (float): Euro Interbank Offered Rate (EURIBOR) for three months (daily indicator)

---

### :gear: **Project Workflow**

The goal of this project is to:
1. Clean the raw data from `bank_marketing.csv`.
2. Reformat the data to meet the bank's structural requirements.
3. Split the cleaned data into three separate CSV files:
   - `client.csv`: Data related to the client.
   - `campaign.csv`: Data related to campaign outreach and outcomes.
   - `economics.csv`: Economic indicators used during the campaign.

---

### :memo: **Dependencies:**
- **Pandas**: For data manipulation
- **NumPy**: For handling missing values
- **Python**: For scripting

To install the necessary dependencies, use the following command:
    
    pip install pandas numpy

---

### How to Use:

1. Clone or download the repository.
2. Run the script (`data_cleaning.py`) to clean and split the data.
3. The cleaned files will be saved in the `cleaned_data/` folder.

---

### 🤝 Support

Contributions, issues, and feature requests are always welcome! If you find this project helpful or interesting, don't forget to give it a ⭐️!

Feel free to open an issue for any questions or suggestions.
