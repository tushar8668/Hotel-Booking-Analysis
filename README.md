# Hotel Bookings Exploratory Data Analysis
## Objective
We are provided with a hotel bookings dataset. 
Out main objective is perform EDA on the given dataset and draw useful conclusions about general trends in hotel bookings and how factors governing hotel bookings interact with each other.
## Dataset
We are given a hotel bookings dataset. This dataset contains booking information for a city hotel and a resort hotel. It contains the following features.
```
- hotel: Name of hotel ( City or Resort)
- is_canceled: Whether the booking is canceled or not (0 for no canceled and 1 for canceled)
- lead_time: time (in days) between booking transaction and actual arrival.
- arrival_date_year: Year of arrival
- arrival_date_month: month of arrival
- arrival_date_week_number: week number of arrival date.
- arrival_date_day_of_month: Day of month of arrival date
- stays_in_weekend_nights: No. of weekend nights spent in a hotel
- stays_in_week_nights: No. of weeknights spent in a hotel
- adults: No. of adults in single booking record.
- children: No. of children in single booking record.
- babies: No. of babies in single booking record. 
- meal: Type of meal chosen 
- country: Country of origin of customers (as mentioned by them)
- market_segment: What segment via booking was made and for what purpose.
- distribution_channel: Via which medium booking was made.
- is_repeated_guest: Whether the customer has made any booking before(0 for No and 1 for Yes)
- previous_cancellations: No. of previous canceled bookings.
- previous_bookings_not_canceled: No. of previous non-canceled bookings.
- reserved_room_type: Room type reserved by a customer.
- assigned_room_type: Room type assigned to the customer.
- booking_changes: No. of booking changes done by customers
- deposit_type: Type of deposit at the time of making a booking (No deposit/ Refundable/ No refund)
- agent: Id of agent for booking
- company: Id of the company making a booking
- days_in_waiting_list: No. of days on waiting list.
- customer_type: Type of customer(Transient, Group, etc.)
- adr: Average Daily rate.
- required_car_parking_spaces: No. of car parking asked in booking
- total_of_special_requests: total no. of special request.
- reservation_status: Whether a customer has checked out or canceled,or not showed 
- reservation_status_date: Date of making reservation status.
```


- Total number of rows in data: 119390
- Total number of columns: 32
## Data Cleaning and Feature Engineering

### (1) Removing Duplicate rows
All duplicate rows were dropped.
### (2) Handling null values
- Null values in columns `company` and `agent` were replaced by 0.
- Null values in column `country` were replaced by 'others'.
- Null values in column `children` were replaced by the mean of the column.
  
### (3) Converting columns to appropriate data types
- Changed data type of `children`, `company`, `agent` to int type.
- Changed data type of `reservation_status_date` to date type.
### (4) Removing outliers
- One outlier was found in the `adr` column. Simply dropped it.
### (5) Creating new columns
- Created new column `total_stay` by adding `stays_in_weekend_nights`+`stays_in_week_nights`.
- Created new column `total_people` by adding `adults`+`children`+`babies`.

## Exploratory Data Analysis

Performed EDA and tried answering the following questions:

```
(1) How Many Booking Were Cancelled?
(2) what is the percentage of cancelled and not cancelled Bookings ?
(3) Which room type is in most demand?
(4) what is the percentage of booking in Resort Hotel and City Hotel ?
(5) Check how many bookings are canceled according to hotel type ?
(6) What is the percentage of booking for each year ?
(7) what type of customers make most number of Bookings ?
(8) In which month Hotels are very Busy ?
(9) According to the hotels, Which month generates the high revenue ?
(10) which distribution channel makes the better revenue generating deals ?
(11) which channels has maximum waiting time ?
(12) From which country most guests come ?
(13) How Long People Stay in the hotel ?
(14) which agent makes most number of bookings ?
(15) Which was the most booked accommodation type (Single, Couple, Family) ?
(16) check relation between the features ?
(17) Not getting the same room will affect on adr or not ?
```

Mainly performed using Matplotlib and Seaborn library and the following graph and plots had been used:
   - Bar Plot.
   - Histogram.
   - Scatter Plot.
   - Pie Chart.
   - Line Plot.
   - Heatmap.
   - Box Plot

## Inferences and Conclusion
```
1. Around 60% bookings are for City hotel and 40% bookings are for Resort hotel, therefore City Hotel is busier than Resort hotel. Also the overall adr of City hotel is slightly higher than Resort hotel.
2. Mostly guests stay for less than 5 days in hotel and for longer stays Resort hotel is preferred.
3. Both the hotels type having significant rate of cancellation. in city hotels cancellation rate is almost 30% and 25% in resort hotels.
4. Most of the guests came from european countries, with most of guests coming from Portugal.
5. Guests use different channels for making bookings out of which most preferred way is TA/TO.
6. Transient type of customers are also made the most number of bookings.
7. For hotels higher adr deals come via GDS channel, so hotels should increase their popularity on this channel.
8. Not getting same room as reserved, do not affect cancellation of bookings. Although different room allotment do lowers the adr.
9. July- August are the most busier and profitable months for both of hotels. 
10. more number of peoples comes when adr is low. and as adr increases then total stay of peoples are decreases.
11. Couples and Single are the most common guests for hotels, hence hotels can plan services according to couples and Single needs to increase revenue.
12. More numbers of Bookings are done by agent no. 9 we have to incourage top 10 agents so they makes more numbers of bookings countiniously.
13. we see that customer stay minimum 7 days in hotels and customers will prefer to stay in city hotels for shorter period but longer period they will prefer to stay in resort hotels.
14. Most demanded room type is A. Hotels should increase numbers of rooms for type A to maximize their revenue.
15. For customers, generally the longer stays (more than 15 days) can result in better deals in terms of low adr.

And many more conclusions....
```
## Challenges
```
(1) There was a lot of duplicate data.
(2) Data was present in wrong datatype format.
(3) Choosing appropriate visualization techniques to use was difficult.
(4) A lot of null values were there in the dataset.
