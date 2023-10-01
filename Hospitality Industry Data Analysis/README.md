# Hospitality Industry Data Analysis

## Task Overview

In response to the COVID-19 pandemic's impact on the hospitality industry, we are tasked with analyzing booking patterns and assessing revenue vs. losses for small to medium businesses. Our goal is to provide essential business reporting and visualizations to support critical decision-making.

## Input Data

We have access to several datasets to perform our analysis:

1. **Booking Data**: Contains booking-related information.
2. **Squad Mapping**: Maps multiple cities to squads.
3. **Property Details**: Provides targeted revenue data for each property.
4. **Primary-ID to Property ID Mapping**: Maps property IDs to primary IDs.

Each dataset contains detailed information about its columns, which we will use for our analysis.

## Output Data

Certainly, here is the Output Data presented in table format:

**Table 1: Squad-level Metrics**

![image](https://github.com/Nasir151/Microsoft-Excel-Projects/assets/94509995/c5a0f8ac-11c6-4dc9-9f50-ec2e1084f390)

In this table:

- **Squad**: The squad identifier.
- **created_at**: The booking creation date (BCD).
- **total_revenue_per_day**: Total revenue generated for each squad on the booking creation date (BCD). This includes bookings for any future dates.
- **current_month_revenue_per_day**: Total revenue generated for each squad on the BCD but limited to bookings for the same month.
- **room_nights_per_day**: The total number of room nights booked for each squad on the BCD.
- **total_cancellation_nights_per_day**: The number of booking nights canceled for each squad on the BCD.
- **total_cancellation_value_per_day**: The revenue lost due to canceled bookings for each squad on the BCD.
- **total_booking_per_month**: The total revenue generated for each squad in the current month (the month corresponding to the BCD).
- **total_room_nights_per_month**: The total number of room nights booked for each squad in the current month.

This table provides a summary of key metrics for each squad, helping businesses track and analyze their performance in the hospitality industry.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### Question 1: As we went through the assignment and understood the expectation, we realized that for all KPIs, we have to calculate wrt squad and BCD (booking created_at date). Let’s set up the first columns of our final report.

![image](https://github.com/Nasir151/Microsoft-Excel-Projects/assets/94509995/f0610f67-7be1-4f4f-b067-ede1f8ea2632)

    Row column can be easily added (highlighted in yellow) 
    We need to create and fill the squad and created_at column with correct values (highlighted in red)

Let’s see the “created_at” column first.

1.1: From which dataset can we get “Booking created at Date (BCD)”?

1.2: After we figure out “Booking created at Date (BCD)” data, we need squad data for the respective booking date. Let’s get appropriate squad data. As we need two columns together, which dataset is most appropriate to get “squad” information wrt the “Booking created at Date (BCD)” data?

1.3: What are the common keys (column) between the “Booking Data” and “Squad Mapping” datasets?

1.4: Is it possible that the same squad can have multiple bookings on any given day? For example, can squad “Himachal Pradesh” have multiple bookings on 2021-03-05 or 2021-03-18? We will urge you to analyze the dataset to answer this question.

1.5: As we are analyzing the data based on squad and for each booking created at date (BCD), How many unique combinations of (Squad, BCD) do we have?

#### Question 2: now, let’s work on the next column, i.e total_revenue_per_day

![image](https://github.com/Nasir151/Microsoft-Excel-Projects/assets/94509995/d7fc9ab6-0b4c-4ecf-806d-bb4547104486)

    We are currently solving total_revenue_per_day (highlighted in red) 

Let’s understand the KPI properly, which will help us implement it right.

It says, “Total revenue for each Squad at BDC (THAT booking created date). This could be for any booking dates, be it next month or same month or any date in the future.”

So for the squad “Himachal Pradesh,” we need to calculate “total_revenue_per_day” for 2021-11-08.

By the way, Do check the “booking data” for “Himachal Pradesh” and “2021-11-08”. You will find many bookings on the same day hence we need to find aggregated revenue of all records.

Let’s understand it further, What does a bolded statement mean?

Total revenue for each Squad at BDC (THAT booking created date). This could be for any booking dates, be it next month or same month or any date in the future.

2.1: What is the Total Revenue Per Day (total_revenue_per_day) for the “Uttarakhand” squad on “2021-05-01”?

#### Question 3: Now, let’s solve “current_month_revenue_per_day

![image](https://github.com/Nasir151/Microsoft-Excel-Projects/assets/94509995/c11719c3-0323-4022-b068-89251b75d4b3)

What does it mean?

It means “Total revenue for each Squad at BDC (THAT booking created date). This only needs to be bookings for the same month and not any other months.

    HINT: Use Check-in and check-out date to identify if the booking is for the same month or next”

As per the example given, we need to calculate the total revenue for November only as we are currently looking at “2021-11-08” BCD. Make sense?

It is already highlighted in the KPI explanation that you need to calculate revenue from the bookings (i.e., check-in and checkout) for the same month and not any other months.

Let’s try to identify booking records for the same month or any other months

Which records fall under the same month from the following dates (created_at - checkin - checkout)?

    Note: You can check this data yourself by filtering squad “Himachal Pradesh” with and created_at with “2021-11-08”

![image](https://github.com/Nasir151/Microsoft-Excel-Projects/assets/94509995/f0d871c4-3ff4-4204-b47e-ad23dff2f745)

3.1: Now you have identified this manually for few records but we have 13436 records hence we can’t do the same for all records. Create an additional column in the “Booking data” to check how many records are where which has bookings(i.e., check-in and checkout) in the same month as the booking created_at date (BCD).

3.2: Let’s explore the bookings more in-depth! Find out the no. of bookings(i.e., check-in and checkout) which ends in the same irrespective of booking created_at date (BCD). Submit your answer below.

3.3: Find out the no. of bookings(i.e., check-in and checkout) where checkin happened in one month, for example, 2021-05-24, and checkout happened in the next month, i.e., 2021-06-03. Please consider the year while solving the problem.

3.4: Find out the no. of bookings(i.e., check-in and checkout) where checkin happened in one month, for example, 2021-05-15, and checkout happened in the next to next month i.e., after 2 months, i.e., 2021-07-14.

#### Question 4: What is “current_month_revenue_per_day” for the “Lonavala” squad on “2021-05-01”?

#### Question 5: What is “current_month_revenue_per_day” for the “Lonavala” squad on “2021-06-15”?

#### Question 6: What is “current_month_revenue_per_day” for the “Alibaug” squad on “2021-05-31”?

#### Question 7: What is “current_month_revenue_per_day” for the “Ooty” squad on “2021-02-26”?

#### Question 8: What is “current_month_revenue_per_day” for the “Lonavala” squad on “2021-02-27”?

#### Question 9: What is “current_month_revenue_per_day” for the “Himachal Pradesh” squad on “2021-07-14”?

#### Question 10: What is “current_month_revenue_per_day” for the “Nashik + Pune” squad on “2021-06-26”?

#### Question 11: What is “room_nights_per_day” for the “Ooty” squad on “2021-12-20”?

#### Question 12: What is “room_nights_per_day” for the “Goa” squad on “2021-05-04”?

#### Question 13: What is “total_cancellation_nights_per_day” for the “Ooty” squad on “2021-04-14”?

#### Question 14: What is “total_cancellation_value_per_day” for the “Ooty” squad on “2021-12-20”?

#### Question 15: What is “total_booking_per_month” for the “Ooty” squad on “2021-12-20”?

#### Question 16: What is “total_room_nights_per_month” for the “Ooty” squad on “2021-12-20”?
