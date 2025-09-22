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

1. Fraud Detection

- Identify suspicious customers with a high number of fraud flags.
- Detect regions with high volumes of fraudulent transactions.
- Provide early-warning signals to strengthen fraud prevention.

2. Customer Transaction Profiling

- Profile customers based on account activity, including card usage, habitual transactions, debts, demographics, per capita income, and yearly income.
- Differentiate between high-risk and low-risk customers to improve monitoring and targeting.

3. Debt & Credit Risk Analysis

- Identify customers with high repayment risk through credit score grouping.
- Highlight heavily indebted customers to support credit decision-making and risk management.

4. Account Acquisition Insights

- Analyse top regions by number of accounts opened per year.
- Investigate the drivers behind spikes in new account openings, providing insights for marketing and strategic expansion.

  ## Data Processing
  --
  Transaction Dataset had 13M rows

  1. Card Data
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
