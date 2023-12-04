# Loan-Data
Data Cleaning and preprocessing of the Loan Data using NumPy in Python

**Details about attributes of Loan Data before Data Cleaning and Preprocessing.**

-	id: A unique LC assigned ID for the loan listing.
-	issue_d: The month in which the loan was funded.
-	loan_amnt: The listed amount of the loan applied for by the borrower. If at some point in time, the credit department reduces the loan amount, then it will be reflected in this value.
-	funded_amnt: The total amount committed to that loan at that point in time.
-	term: The number of payments on the loan. Values are in months and can be either 36 or 60.
-	int_rate: Interest Rate on the loan
-	installment: The monthly payment owed by the borrower if the loan originates.
-	grade: LC assigned loan grade.
-	sub_grade: LC assigned loan subgrade.
-	verification_status: Indicates if the borrower’s income was verified by LC, not verified, or if the income source was verified.
-	url: URL for the LC page with listing data.
-	addr_state: The state provided by the borrower in the loan application.
-	total_pymnt: Payments received to date for the total amount funded.


**Transformations made to the attributes of Loan Data for Data Cleaning and Preprocessing.**

-	Id: Sorted in increasing order. 
-	issue_d: Name changed to issue_date. Transformed into numbers from 0 to 12. 
-	loan_amnt: Name changed to loan_amnt_USD. Created an equivalent value in _EUR stored in loan_amnt_EUR.
-	loan_status: Transformed into a dummy variable (0 or 1).
-	funded_amnt: Name changed to loan_amnt_USD. Created an equivalent value in _EUR stored in loan_amnt_EUR.
-	Term: Name changed to term_months. Removed " months" and transformed all the data into numbers.
-	int_rate: Transformed from percentages to values between 0 and 1 (e.g. 33.8 -> 0.338).
-	installment: Name changed to loan_amnt_USD. Created an equivalent value in _EUR stored in loan_amnt_EUR.
-	Grade: Dropped. (Can be generated from sub_grade.)
-	sub_grade: Transformed into a numeric variable ranking each subgrade from best (1) to worst (36).
-	verification_status: Transformed into a dummy variable (0 or 1).
-	url: Dropped. (Can be generated from id.)
-	addr_state: Name changed to state_address. The values are split into 4 geographical territories - East, West, South, and Midwest.
-	total_pymnt: Name changed to total_pymnt_USD. Created an equivalent value in _EUR stored in total_pymnt_EUR.
-	exchange_rate: Added to each account based on the value in issue_date.


**Final details and names of attributes after Data Cleaning and Preprocessing.**

-	Id: A unique LC assigned ID for the loan listing.
-	loan_amnt_USD: The listed amount of the loan applied for by the borrower, in US dollars. If at some point in time, the credit department reduces the loan amount, then it will be reflected in this value.
-	loan_amnt_EUR: The listed amount of the loan applied for by the borrower in Euro. If at some point in time, the credit department reduces the loan amount, then it will be reflected in this value.
-	funded_amnt_USD: The total amount committed to that loan at that point in time in US dollars.
-	funded_amnt_EUR: The total amount committed to that loan at that point in time in Euro.
-	int_rate: Interest Rate on the loan.
-	installment_USD: The monthly payment owed by the borrower if the loan originates.
-	installment_EUR: The monthly payment owed by the borrower if the loan originates.
-	total_pymnt_USD: Payments received to date for the total amount funded in US dollars.
-	total_pymnt_EUR: Payments received to date for the total amount funded in Euro. 
-	exchange_rate: The EUR/USD exchange rate at the time of the loan application.
-	issue_date: The month in which the loan was funded.
-	loan_status: Current status of the loan.
-	term_months: The number of payments on the loan. Values are in months and can be either 36 or 60.
-	sub_grade: LC assigned loan subgrade.
-	verification_status: Indicates if the borrower’s income was verified by LC, not verified, or if the income source was verified.
-	state_address: The state provided by the borrower in the loan application.
