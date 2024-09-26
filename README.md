**SQL PORFOLIO PROJECT** :
 
 **CASE STUDY :

**ANALYSIS OF “CHURNED CUSTOMERS” IN TELECOMMUNICATION INDUSTRY"


A dataset has been provided to us to run an analysis on the “churned customers” of a telecommunication company. In this assignment, we have to find the reasons behind “why the customers are becoming churned”?. Also, they wanted to explore and uncover some “useful insights” which can help in decision making as well as link it to employee emotions and satisfaction too.

**DATA SET :

The dataset contains information about a fictional telco company that provided home, phone and Internet services. It contains some of the variables like:

a. Customer status

b. Demographics

c. Location

d. Population

e. Services

**ANALYSIS** :
The case study required to do an analysis in SQL. Different queries were run to get the desired results. One of the query is done as follows:

QUERY :
— — Considering the top 5 groups with the highest average monthly charges among churned customers, how can personalized offers be tailored based on age, gender, and contract type to potentially improve customer retention rates?
with service as (
select a.`Customer ID`, a.`Contract` as contract_type,
avg(`Monthly Charge`) over (partition by `Customer ID` order by `Monthly Charge` desc) as average_monthly_charges, b.`Customer Status`
from service a
join customer_status b
on a.`Customer ID` = b.`Customer ID`
where b.`Customer Status` = “churned”)
select a.*, b.`Age`, b.`Gender`
from service a
join demographics b
on a.`Customer ID` = b.`Customer ID`
order by a.average_monthly_charges desc
limit 5;

**RESULT** :
All of the top 5 customers who have churned are displayed below with their contract type, average monthly charges , age and gender.
(https://github.com/user-attachments/assets/2bd6c1ab-b0f7-464a-841c-c36d05c87a8f)


RESULT OF “TOP 5 CUSTOMERS WHO HAVE CHURNED”
REASONS BEHIND THE “CHURNED CUSTOMERS”:

After running all the queries and doing the analysis part, I came to find some of the problems which lead to churned customers :

**PROBLEMS** :

1.Limited range of services:
Competitors have been providing better offers with “unlimited service charges “ which in turn made some of these customers leave their companies and go to competitors.

2. Bad offers:

The company had been providing “not good enough” offers to their customers . Hence it made easy for the customers as well to opt for the competitors.

3. Service dissatisfaction :

Customers had not been given proper services with better offers and hence it made them unsatisfied. This has proved to be a “turning point” for the customers and they preferred to switch to other telecommunication companies then.

**SOLUTIONS** :

Following can be some of the ways in which we can solve the issues related to the churned customers in the telecommunication industry.

a. Satisfied service
b. Providing wide range of services
c. Good offers
d. No additional charges
e. Focusing more on the “yearly “ contract type customers.

After the evaluation and analysis part, we were also asked to give suggestions to the telecommunication company so that they “retain their churned customers as well as they can perform better in future as well.”

**INSIGHTS / RECOMMENDATION **
The telecommunication company should be focusing on some the important aspects like :

1. Provide better offers.
2. Provide a wide range of services
3. “Yearly” contract holders should be given some “free service packages”
4. No additional charges for the “new joining customers”
5. Provide better devices which can work well in all places.

— — To wrap up, we can summarize by saying this :

**“If customers in the telecommunications industry receive quality services,
improved devices, 
attractive offers,
and are not overcharged for long calls, it can result in reduced customer churn and improved future performance.”**
