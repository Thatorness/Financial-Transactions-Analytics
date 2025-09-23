# Financial Transactions Analysis
---
The dataset analysed basically to understand user's behaviour through transactions initiated, detect fraudulent transactions by individuals across regions
The dataset consists of

 - User's data 
   - Demographic information about customers, 
   - Account related details such as: (Client ID, Age group, Credit score, Geolocation, Retirement age, Years to retirement, Yearly Income etc..)
- Transactions data
   - Covers transactions throughout 2010s
   - Features transaction types, amounts, and merchant location
   - Time and Date, Declined transactions error messages, Transaction Channels etc..
 - Cards data -
   - Card brands, Card type, Number of cards issueed, expiration date etc..

## Problem Statement
---
Financial institutions face significant challenges in detecting fraud, profiling customer risk, and understanding account acquisition trends. This project leverages transactional, demographic, and financial data to uncover hidden patterns and provide actionable insights across four key areas:

#### 1. Fraud Detection

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
- Age Group - Under 30 is less than 30 years old, less than 50 years is middle aged, above 50 years is old.
- Retirement Age – Expected retirement age.
- Years to Retirement (Y2R) - Number of years left to retirement age
- Y2R Grouping - Less than 0 is retired, less than 30 mid career, above 30 years is early career
- Birth Year / Birth Month – Birth details.
- Gender – Gender of the customer.
- Address – Customer’s primary address.
- Latitude / longitude – Geolocation of the address.
- Per Capita Income – Income per household member in customer’s area.
- Per Capita Grouping - less than $25k low, less than $45k medium, above $40k is high.
- Yearly Income – Annual income of the customer.
- Total Debt – Outstanding debt held by the customer.
- Debt to Income Ratio: A customer's ability to repay current debt based on yearly income
- Credit Score – Credit rating of the customer.
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
- merchant_state – State where the transaction occurred.
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

---

## Approach / Methodology

Step 1: Data cleaning & joining (transactions + cards + users).

Step 2: Exploratory Data Analysis: Categorized transactions into 
  -  Successful: Transactions without error messages
  -  Genuine declined transactions: Transactions declined due to technical glitch
  -  Customer issue: Transactions declined due to insufficient balance
  -  Attempted fraud: Transsactions carried out via chip, swipe and online with error message with keywords such as Bad card number, Bad CVV, Bad Expiration, and Bad Zip code
  -  Medium risk transaction: Chip and swipe transactions with Bad Pin, there weren't online transactions with Bad Pin in the dataset.
     -   Further categorized into:
  -  Fraud - Attempted and Medium risk
  -  Non Fraud - Customer issue and Genuine declined transactions

Step 3: Visualisation in Power BI (top fraud clients, fraud by location, transaction amounts, etc..).

## Result
Key Insights

From exploratory analysis and Power BI dashboards:

Fraud Patterns: Most fraudulent transactions occurred during late-night hours were associated with unusual merchant locations outside the customer’s normal region.

Transaction Behaviour: Fraudulent transactions often had higher-than-normal amounts compared to the client’s historical average.

Top Clients / Regions: A small subset of clients accounted for a disproportionately high number of flagged transactions. Certain regions showed clusters of suspicious activity.

Customer Profiling: Customers with higher debt-to-income ratios and lower credit scores were more likely to exhibit risky transaction behaviour.
