# Financial Transactions Analysis
---
The dataset analyzed basically to understand user's behavior through transactions initiated, detect fraudulent transactions by individuals across regions
The dataset consists of

 - User's data 
   - Demographic information about customers, 
   - Account related details such as: (Client ID, Age group, Credit score, Geolocation, Retirement age, Years to retirement, Yearly Income etc..)
- Transactions data
   - Covers transactions throughout 2010s
   - Features transaction types, amounts, and merchant location
   - Time and Date, Declined transactions error messages, Transaction Channels etc..
 - Cards data -
   - Card brands, Card type, Number of cards issued, expiration date etc..

## Problem Statement
Financial institutions face significant challenges in detecting fraud, profiling customer risk, and understanding account acquisition trends. This project leverages transactional, demographic, and financial data to uncover hidden patterns and provide actionable insights across four key areas:

### 1. Fraud Detection

- Identify suspicious customers with a high number of fraud flags.
- Detect regions with high volumes of fraudulent transactions.
- Provide early-warning signals to strengthen fraud prevention.

### 2. Customer Transaction Profiling

- Profile customers based on account activity, including card usage, habitual transactions, debts, demographics, per capita income, and yearly income.
- Differentiate between high-risk and low-risk customers to improve monitoring and targeting.

### 3. Debt & Credit Risk Analysis

- Identify customers with high repayment risk through credit score grouping.
- Highlight heavily indebted customers to support credit decision-making and risk management.

### 4. Account Acquisition Insights

- Analyse top regions by number of accounts opened per year.
- Investigate the drivers behind spikes in new account openings, providing insights for marketing and strategic expansion.

  ## Data Description 
### 1. User Data
Contains demographic and financial information about each customer.
- Client ID – Unique identifier for the customer.
- Current Age – Current age of the customer.
- Age Group - Under 30 = Young, 30–49 = Middle-aged, 50+ = Old.
- Retirement Age – Expected retirement age.
- Years to Retirement (Y2R) - Number of years left to retirement age
- Y2R Grouping - Less than 0 = Retired, 0–29 = Mid-career, 30+ = Early-career.
- Birth Year / Birth Month – Birth details.
- Gender – Gender of the customer.
- Address – Customer’s primary address.
- Latitude / longitude – Geolocation of the address.
- Per Capita Income – Income per household member in customer’s area.
- Per Capita Grouping - < $25K = Low, $25K–$44.9K = Medium, ≥ $45K = High.
- Yearly Income – Annual income of the customer.
- Total Debt – Outstanding debt held by the customer.
- Debt to Income Ratio: A customer's ability to repay current debt based on yearly income
- Credit Score – Credit rating of the customer.
- Credit Grouping - <580 = Low, 580–699 = Medium, ≥700 = High.
- Number of Credit Cards – Total number of credit cards owned.

### 2. Transactions Data
Captures 13M unique financial transactions made using cards.
- Trxn Id – Unique identifier for each transaction.
- date – Timestamp of the transaction.
- Client Id – Customer who performed the transaction.
- Card Id – Card used for the transaction.
- Amount – Transaction value.
- Transaction Channel – Either Swipe, Chip or Online transaction.
- Merchant Id – Unique identifier of the merchant.
- Merchant City – City where the transaction occurred.
- Merchant State – State where the transaction occurred.
- Zip – ZIP code of the merchant location.
- Mcc – Merchant Category Code (type of business).
- Errors – Transaction errors, (e.g., declined, insufficient funds).

### 3. Card Data
Contains details of payment cards issued to customers.
- ID – Unique identifier for each card.
- Client ID – Customer who owns the card.
- Card Brand – Card network (e.g., Visa, MasterCard, etc.).
- Card Type – Credit or debit card classification.
- Card Number – Masked card number for transactions.
- Expires – Card expiry date.
- CVV – Security code.
- Transaction channel – Indicates if the card has a chip (Y/N).
- Number of Cards Issued – Number of cards issued to the customer.
- Credit Limit – Maximum credit line available.
- Account opening Date – Date when the account was opened.
- Year of Last Pin change – Last year the PIN was updated.
- Card on Dark web – Flag showing if the card has appeared in known breaches.

## Approach / Methodology

Step 1: Data cleaning & joining (transactions + cards + users).

Step 2: Exploratory Data Analysis: Categorized transactions into 
  -  Successful: Transactions without error messages
  -  Genuine declined transactions: Transactions declined due to technical glitch
  -  Customer issue: Transactions declined due to insufficient balance
  -  Attempted fraud: Transactions carried out via chip, swipe and online with error message with keywords such as Bad card number, Bad CVV, Bad Expiration, and Bad Zip code
  -  Medium risk transaction: Chip and swipe transactions with Bad Pin, there weren't online transactions with Bad Pin in the dataset.
     -   Further categorized into:
  -  Fraud - Attempted and Medium risk
  -  Non Fraud - Customer issue and Genuine declined transactions

Step 3: Visualisation in Power BI (top fraud clients, fraud by location, transaction amounts, etc..).


## Result
Key Insights

From exploratory analysis and Power BI dashboards:

- Fraud Patterns: Most fraudulent transactions occurred during late-night hours were associated with unusual merchant locations outside the customer’s normal region.

- Transaction Behaviour: Fraudulent transactions often had higher-than-normal amounts compared to the client’s historical average.

- Top Clients / Regions: A small subset of clients accounted for a disproportionately high number of flagged transactions. Certain regions showed clusters of suspicious activity.

- Customer Profiling: Customers with higher debt-to-income ratios and lower credit scores were more likely to exhibit risky transaction behaviour.

- Account Acquisition: The spike in 2020 was largely driven by younger demographics. This trend may be linked to increased employment opportunities in the regions, which could have enhanced financial inclusion and encouraged new account openings

## Conclusion
Fraud rates have been effectively controlled, with only 0.4% of transactions identified as fraudulent over the past nine years.

- A notable pattern of North American workers migrating to Europe was observed, as many clients reported registered addresses in North America.

- Online transactions continue to be the most vulnerable to fraudulent activity.

- The high debt-to-income ratio, particularly in Sweden, suggests either unusually low per capita income or excess liquidity in the region.

---
