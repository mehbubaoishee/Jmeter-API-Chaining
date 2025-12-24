# JMeter API Chaining Assignment

**Name:** Mehbuba Alam Oishee   
**Topic:** Performance Testing  
**Assignment:** JMeter API Chaining (Dmoney)

## Project Description

This project is based on **API chaining using Apache JMeter** for the **Dmoney system**.  
The objective of this assignment is to design a JMeter test plan (`dmoney.jmx`) that simulates multiple transaction scenarios using dynamic data and validates successful execution using assertions.
The test plan is created using the **Dmoney API collection** and focuses on deposits, send money, and payment transactions.


## Dmoney API Details

**User API:**  
https://dmoney.roadtocareer.net/api-docs/user/

**Transaction API:**  
https://dmoney.roadtocareer.net/api-docs/transaction/

**Portal Login:**  
https://dmoneyportal.roadtocareer.net/login  

**Admin Credentials:**  
- Email: `admin@dmoney.com`  
- Password: `1234`

## Test Scenario
The following scenarios are implemented using **API chaining**:
- **5 agents** perform **deposit** transactions for **10 customers**
- **5 customers** send money to **another 10 customers**
- **5 customers** make **payments** to **2 merchants**

## Test Design & Implementation
- Logged in **once as admin** and generated a token
- The generated token is reused across all thread groups
- Created **3 separate Thread Groups** under the Test Plan:
  - Deposit Thread Group
  - Send Money Thread Group
  - Payment Thread Group
- Each Thread Group has a **ramp-up time of 120 seconds**
- Used **CSV Data Set Config** for dynamic user data:
  - `deposit.csv`
  - `sendMoney.csv`
  - `payment.csv`
- Used **Random Variable Controller** to generate dynamic transaction amounts
- Used **small transaction amounts** to prevent balance exhaustion
- Added **Assertions** to verify that all transactions are successful

## Technology & Tools Used
- **Apache JMeter** – API chaining and test execution
- **CSV Data Set Config** – dynamic test data
- **Random Variable Controller** – dynamic transaction amount
- **Response Assertions** – validation of successful transactions
- **HTML Dashboard Report** – performance report generation
- **Git & GitHub** – version control and assignment submission

## How to Run the Test
1. Open **Apache JMeter**
2. Load the file `dmoney.jmx`
3. Ensure CSV file paths are correctly set
4. Run the test plan
5. Generate HTML report using: jmeter -n -t "F:/path/to/your/dmoney.jmx" -l results.jtl -e -o dashboard
6. Open `dashboard/index.html` in browser

## Test Results


## Notes
- This assignment focuses on **API chaining**, not full-scale performance testing
- Excel documentation is not included as per assignment instructions

