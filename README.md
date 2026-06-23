# The Lead Time Dilemma: Reducing Patient No-Shows Through Data Analytics

Missed appointments create significant operational challenges for healthcare providers, leading to underutilized clinical capacity, increased overhead costs, and reduced patient access to care.
This project analyzes over 100,000 medical appointment records to identify the primary drivers of patient no-shows and develop data-driven scheduling strategies that improve clinic efficiency. Using Python, Pandas, NumPy, Matplotlib, and Seaborn, I transformed raw healthcare data into actionable operational insights.
## Business Questions

This analysis was designed to answer three key questions:
What is the overall impact of patient no-shows?
Which patient and operational factors influence attendance?
How does appointment lead time affect no-show probability?

## Tools & Technologies
Python
Pandas
NumPy
Matplotlib
Seaborn
Jupyter Notebook

## Data Preparation & Feature Engineering
The dataset contained over 100,000 appointment records, including scheduling dates, appointment dates, demographic information, SMS reminder status, and attendance outcomes.
To better understand patient behavior, I engineered a new feature called Lead Time, defined as the number of days between appointment scheduling and the appointment date.

df['LeadTime'] = (df['AppointmentDay'] - df['ScheduledDay']).dt.days

Appointments were then grouped into booking cohorts to measure how waiting time influenced attendance behavior.

## Key Findings
1. No-Shows Create Significant Capacity Loss
Analysis revealed an overall no-show rate of approximately 20%, meaning one out of every five scheduled appointments resulted in unused provider capacity.
This level of missed utilization represents a substantial operational and financial burden for healthcare organizations.

2. Demographics Were Weak Predictors
Variables such as age and patient demographics showed limited predictive value when analyzed independently.
SMS reminders provided a modest improvement in attendance rates but did not fully explain no-show behavior.

3. Appointment Lead Time Was the Strongest Predictor
The most influential factor was the number of days between scheduling and the appointment date.

<img width="542" height="129" alt="Screenshot 2026-06-23 at 2 14 17 PM" src="https://github.com/user-attachments/assets/f16626d3-40a5-4259-8779-baef15c0f140" />

The analysis revealed a clear behavioral tipping point: once appointments were scheduled more than three days in advance, no-show rates increased dramatically and continued to rise as lead times lengthened.

## Visualization

The chart below illustrates the relationship between booking lead time and no-show probability.

<img width="457" height="831" alt="Screenshot 2026-06-23 at 2 15 36 PM" src="https://github.com/user-attachments/assets/91892adf-8125-4300-8e33-e8313b5086a1" />

The visualization demonstrates a consistent increase in no-show rates as appointment wait times grow, highlighting lead time as a critical operational lever.

## Business Recommendations

### Optimize Scheduling Windows
Where operationally feasible, prioritize shorter scheduling windows for routine appointments to capture higher-intent patients and reduce missed visits.
### Enhance Long-Lead Appointment Outreach
Implement multi-touch reminder campaigns for appointments scheduled more than two weeks in advance, including confirmation requests at 7-day, 3-day, and 24-hour intervals.
### Develop Predictive Scheduling Models
Use historical no-show probabilities to inform strategic overbooking policies for high-risk appointment slots and improve overall provider utilization.

## Conclusion
This project demonstrates how feature engineering and exploratory data analysis can uncover operational bottlenecks hidden within large healthcare datasets.
By identifying appointment lead time as the primary driver of no-show behavior, the analysis provides a practical framework for improving clinic utilization, reducing wasted capacity, and enhancing patient access to care.


