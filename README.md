# Lending Club Case Study
- Lending club case study is a project which helps Lending Club Institution to determine whether they should approve or deny any coming loan request from the applicants. It also helps to reduce the financial/credit loss of Institution. **The main objective of our case study is to find defaulter or risky applicants, those can't continue to pay the complete loan amount**. We have done analysis on the given loan dataset and found some driver variables by which Lending Club Institute can predict or identify the applicants who may be defaulter's and Lending Club Institute can decide to approve loan request of these defaulter's.


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)


## General Information
- Project is related to Consumer Finance Company, who provides various types of loan to customers. This company is the largest online loan marketplace where it facilitates different type of loans such as Personal loan, business loan, home loan and loan for medical procedures.So this project is about to find the driver variables by using which company can decide whether they should give loan to a customer or not.
When any finance company receive any loan application than they do their calculation with respect to the applicant's profile and make decision whether they should give loan to the applicant or not.
In this process there are some **risk analysis**:
    - To identify the person able to repay the loan : 
        - In this case if we give loan to the person which is likely to be default then it is **financial loss** and if we don't give loan to the person who is able to repay the loan then it is **business loss**
So the main concern for finance company is to confirm whether an applicant is likely to be default or not.

- Business problem is totally related to the risk analysis, Company needs to find out the way using which they can make decision for giving loan to an applicant or not, and also needs to confirm there should not be any **Business loss** and **Financial loss**.
In a simple words, we can say that Company needs to find out some way to identify the defaulter so that they can deny to them for any type of loan to reduce the risk of their loss.

- For this case study we are using **loan.csv** dataset and also **Data_Dictionay.xlsx** .

So to find the solution for the problem stated above we did some analysis on the given dataset **loan.csv**.

## Data Understanding
    - In this section we understand about the data like what type of data we have, whether it numeric or categorical data.
    - How many rows and columns are in the dataset
    - What are types of those data, whether that type is correct for the data or not.
    - We took help from the Data_Dictionary.xlsx to understand the terms exists in the dataset.

## Data Cleaning
    - So before going to analyse the dataset we need to perform some data cleaning
    - Like in our dataset we did the following for data cleaning:
        - Drop columns having all NaN values
        - Drop columns having same value for each row
        - Drop columns having no impact on the target variable
        - Drop columns having no impact on target variable as these columns are come into existence after getting loan
        - Drop columns having almost same data

## Data Imputation
    - In this phase we have fixed some columns to make them available for any analysis
    - For example to our dataset:
        - Removed "month" string from "Term" column
        - Removed "%", "+", "years" strings also from columns

## Column Data duplicity
    - There were some columns in which data is duplicate 
    - Like for example in emp_title column we have:
        - 'US Army', 'U.S. Army', 'US ARMY', 'United States Army', 'us army'
        - So we have replaced all these with one command value : 'US Army'

## Derived Columns
    - From the existing dataset we have derived some new columns for more analysis
    - Like there is a column 'issue_d', so we got 'Year' and 'Month'
    - Also we create bucket for columns like : loan_amount, annual_inc, int_rate, instalment, DTI etc.

## Missing Values
    - We also find out some columns have very less percentage of NaN values
    - So we put some suggestions to replace those NaN values

- After doing Data understanding, filtering , cleaning, imputing missing values we did different type of analysis:

## Univariate Analysis
    - In this analysis we did Univariate analysis on most of the columns.
    - In Univariate analysis, single column we take and analysis about frequency of that column
    - Like for **term** column we analyse the frequency of customers took loan for 36 months and 60 months

## Segmented Univariate Analysis
    - In Segmented Univariate Analysis, we did analysis of columns against out target variable that is Loan Status
    - By doing segmented analysis we found that what impact of any column on our target column
    - We have provided some recommendation basis of this segmented Univariate analysis

## Bivariate Analysis
    - In Bivariate Analysis, we have added two columns for analysis against the target variable
    - To find out that how these two columns behave with each other against target variable
    - On the basis of that behaviour we have provided some recommendation to Loan provider company

## Driver Variables
    - After doing all the analysis on loan dataset, we have found below driver variables which can play significant role to decide whether bank should approve or deny the loan of the applicants. Below are the driver variables:    
        1. Loan Amount 
        2. Interest Rate
        3. Grade
        4. DTI Ratio
        5. Annual Income
        6. Term
        7. Public Record Bankruptcies


## Conclusions
### Recommendation on the basis of Segmented Univariate Analysis
- Analysis of Loan Status with Loan Amount Bucket
    - It is clearly visualise that if customer took loan amount > 15000 then their chances to be defaulter is high as compare to loan amount < 15000, so for recommendation bank should not approve loan amount > 15000 without doing thoroughly check the documents of the customer.
- Analysis of Loan Status with Term
    - We found that customers are more likely to be defaulter if they take loan for long period (60 months), so to reduce the risk of loss, company should not provide loan for maximum time period to the customer. Better to encourage customer to take loan for shorter period.
- Analysis of Loan Status with Interest Rate Bucket
    - It is clearly showing that if bank gives loan to customer with high interest rate (>16%) then chances to be defaulter of that customer is high. So for recommendation Bank can offer loan to the customer upto 15% interest rate.
- Analysis of Loan Status with Grade
    - As for this analysis we can see that if bank gives loan to the customer who has high grade, here we can say A and B, then chances to be defaulter of that customer is less. And as we move towards the lower grade than chances become high. So better to avoid too give loan to lower graded customers.
- Analysis of Loan Status with Home Ownership
    - When bank gives loan to the customers who comes under Other category means they didn't provide their home ownership detail, their chances to be defaulter is high because bank doesn't have exact information of their home ownership. They might not have better place to live or they may be living at very poor place. So bank should avoid to give loan to Others Category.
- Analysis of Loan Status with Annual Income Bucket
    - Customers having annual income upto 40,000 might have chances to be defaulter and also as we move from (0-40000) to (85001+) annual salary bucket then chances are less. So for suggestion Bank can provide less loan amount to customers having less annual income that is below 40000.
- Analysis of Loan Status with Verification Status
    - It is totally unbelievable - Loan given to not verified customers are showing loyal as compare to verified and source verified. So when an applicant requests for loan then bank should thoroughly inspect all required details whatever they provided to reduce the risk of financial loss.But again although "Not verified" customers are less defaulter still bank should not provide loan to these customers as well blindly.
- Analysis of Loan Status with Purpose
    - From analysis it is clearly showing that loan given to customers who want to start their small business are more defaulter,
    so may be the reason to be defaulter is **failure or loss in the business**. So we can recommend to bank when customer wants loan for any small business than bank should get complete necessary details of customer's business like business type, how it will behave in a long term and other factors as well.
- Analysis of Loan Status with DTI Bucket
    - DTI is very important factor, it is Debt-to-Income ratio, through this ratio we can get data about the customer's expenses against their income. So after doing analysis it's clear that having high DTI ratio ( > 19) chances to be defaulter more. And when moving from DTI bucket (0 - 8) to (19+), chances are also become more. So better to avoid give loan to customer having high DTI ratio that is (> 19).
- Analysis of Loan Status with Public Record
    - Public records means customer having derogatory record or not, so from analysis it is clear that chances to be defaulter for a customer having minimum public record is less as compare to customer having maximum public record. So bank can avoid or deny to provide loan to customer having maximum public records. 
- Analysis of Loan Status with Public Record Bankruptcies
    - Customers having maximum number of public record bankruptcies are likely to be defaulter more if we compare this with customers having 0 or very less (only 1) public record bankruptcies. So for recommendation to bank, they should completely deny the customers with high number of public record bankruptcies to reduce their **financial or business loss**.

### Recommendation on the basis of Bivariate Analysis
- Analysis of Loan Amount Bucket vs Interest Rate Bucket with respect to Loan Status
    - Customers who's borrowing loan more than 16% interest rate whether they are applying loan for amount 5000 or 15000+, their chances to be defaulter high. So our recommendation to bank is, they can provide loan upto 15% interest rate to their customers.
- Analysis of Interest Rate Bucket vs Term with respect to Loan Status
    - Customers who's borrowing loan for a longer term that is for 60 months and if we compare it with Interest rate bucket then it is clearly visible that as we are moving from bucket (0-9) to bucket (16+) interest rate, then chances of customers to be defaulter is more who took loan for longer period. So better to ask customer to apply loan for short period of time with minimum interest rate like upto 12%.
- Analysis of Employee Length vs Loan Amount Bucket with respect to Loan Status
    - Customers who's borrowing loan amount more than 15000 for each category of employee's length(experience), there chances to be defaulter high as compare to other loan amount < 15000. So recommendation to bank, they should try to approve loan request of their customers below 15000.
- Analysis of DTI Bucket vs Annual Income Bucket with respect to Loan Status
    - Customers who's annual income is < 40000 in each DTI ratio bucket, there chances to be defaulter is high. Therefore our recommendation to the bank, they should avoid to approve loan request of the customers who's having low annual income < 40000, in whatever DTI bucket they come.
- Analysis of Annual Income Bucket vs Loan Amount Bucket with respect to Loan Status
    - Customers who took loan amount >15000 are more likely to be defaulter for each category of Annual Income bucket, but it is very high for range (<40000) and (40001 to 60000). Therefore our recommendation to bank, they should provide loan amount <15000 to all the customers come under each annual income bucket, If loan amount > 15000 then bank should thoroughly check all the details of the customer before giving loan to them.
- Analysis of Purpose vs Annual Income Bucket with respect to Loan Status
    - Small Business applicants have high chances to be defaulter. Further customers having annual income upto 40000 apply loan for renewable energy, they also have high chance to be defaulter. Therefore our recommendation to the bank, try to avoid those applicant who applied loan for small business, renewable energy having annual income below 40000.
- Analysis of Public Record Bankruptcies vs Loan Amount Bucket with respect to Loan Status
    - For the customers having number of public record bankruptcies are 2 their chances to be defaulter is very high if they apply loan amount more than 10000 and if number of records are equal to 1 then their might chance to be defaulter for loan amount > 10000.Therefore our recommendation to the bank, they should completely deny the customers apply loan amount > 10000 and having public record bankruptcies 2 and for 1 bank should check details of customer before approve loan amount > 10000.
- Analysis of Home Ownership vs Term with respect to Loan Status
    - Customers who come under Rent, Own, Mortgage category are applied loan for longer term, their chances to be defaulter high. So our recommendation for bank, to insist their customers take loan for short duration whether they come under any category of home-ownership.
- Analysis of Grade vs Loan Amount Bucket with respect to Loan Status
    - Customers having grade D and below towards G are more likely to be defaulter, whatever loan amount they apply and it is getting worst moving towards grade F and G. So our recommendation to bank, they should check all the necessary details required before approve the loan amount for Grade D to G and need to check proper documents to approve loan for grade F and G.


## Technologies Used
- Python - version 3.9.12
- numpy library - version 1.21.5
- pandas library - version 1.4.2
- seaborn library - version 0.11.2
- matplotlib.pyplot library - version 3.5.1
- datatime library
- jupyter notebook - version 6.4.8


## Acknowledgements
Give credit here.
- This project was inspired by Upgrad.com
- References: Help taken from Google.com and Live Sessions on EDA and EDA Module and also from PI sessions


## Contact
- Harish Rathuri - [@harryraturi](https://github.com/harryraturi)
- Anurag Benjwal - [@anuragbenjwal107](https://github.com/anuragbenjwal107)
