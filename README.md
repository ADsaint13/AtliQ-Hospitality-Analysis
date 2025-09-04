# AtliQ Hotels Data Analysis Project

Welcome! This project is a deep dive into the booking data for **AtliQ Hotels**, a leading hospitality chain. The goal wasn't just to crunch numbers, but to tell a story about what drives their business. By cleaning, exploring, and visualizing their data, we've uncovered key patterns in bookings, revenue, and customer behavior.

Think of it as being a data detective for a hotel chain, trying to answer the questions that really matter to the business.

## ❓ The Business Questions We Tackled

We started with a clear set of questions to guide our analysis:

*.  What's the average occupancy rate for different room types (like Standard vs. Presidential suites)?
*.  Which cities are the most occupied?
*.  Are weekends truly busier than weekdays?
*.  Which cities brought in the most revenue in June?
*.  How much revenue does each hotel property generate?
*.  What is the average customer rating in each city?
*.  Which booking platform is the most valuable in terms of revenue?

## 🗂️ The Data: Our Five Key Files

Our investigation was fueled by five key datasets, each telling a part of the story:

* **`fact_bookings.csv`**: The heart of our data, containing every single booking transaction. This told us *what* happened.
* **`fact_aggregated_bookings.csv`**: A handy summary of daily bookings and room capacities.
* **`dim_hotels.csv`**: Our "who's who" of hotels, listing their names, cities, and categories (Luxury vs. Business).
* **`dim_rooms.csv`**: The decoder ring for room types, turning codes like `RT1` into `Standard`.
* **`dim_date.csv`**: Our calendar expert, telling us if a date was a weekday or a weekend.

## ⚙️ Our Process: A Step-by-Step Journey

**1. Loading & First Look**
Like any good analysis, we started by loading all the CSV files into pandas DataFrames. We took a quick peek at the data to understand its shape and what we were dealing with.

**2. Cleaning the Mess**
Real-world data is rarely perfect! We rolled up our sleeves and performed some crucial cleaning:
* **Invalid Guests:** We found some bookings with negative guest numbers (a clear error!) and removed them.
* **Revenue Outliers:** A few revenue entries were astronomically high, likely due to typos. To prevent them from skewing our results, we filtered them out using a 3-standard deviation rule.
* **Missing Capacity:** A couple of entries were missing room capacity data. We filled these gaps with the median capacity, a safe and robust choice.

**3. Getting the Data Ready (Transformation)**
With clean data, it was time to make it more powerful.
* We engineered a key metric: **Occupancy Percentage (`occ_pct`)**, which is crucial for measuring performance.
* We then merged all our separate tables into one master DataFrame. This gave us a complete picture for every booking, combining the 'what' (bookings) with the 'who' and 'where' (hotel and room details).

## 💡 Key Findings & Insights

* Weekend Occupancy is Significantly Higher: There is a clear pattern of higher bookings during weekends. The average occupancy rate on weekends is approximately 72.34%, compared to a much lower 50.88% on weekdays.

* Delhi Leads in Occupancy, but Mumbai Generates the Most Revenue: Delhi hotels consistently show the highest average occupancy rate at 61.5%. However, Mumbai is the top city for revenue generation, realizing over 668 million, while Delhi generated the least at 294 million. This suggests higher room prices or longer stays in Mumbai.

* Top Performing Property: The "Atliq Exotica" property stands out as the highest-performing hotel, generating the most realized revenue among all properties in the chain.

* Room Category Performance is Consistent: Occupancy rates are relatively stable across all room types (Standard, Elite, Premium, and Presidential), with averages hovering between 57% and 59%. Presidential suites have a slightly higher average occupancy at 59.28%.

* Customer Ratings Vary Slightly by City: Customer satisfaction, as measured by ratings, is highest in Delhi with an average rating of 3.78. Bangalore has the lowest average rating at 3.41.

* June Performance: The analysis for the month of June shows that Delhi maintained its lead in occupancy with a rate of 62.47%.

* Booking Platform Contribution: The analysis includes a breakdown of revenue realized per booking platform, which helps identify the most financially significant channels for the business.

* This analysis provides a solid foundation for AtliQ Hotels to make smarter, data-driven decisions about marketing, pricing, and operations.

## 🛠️ Tools Used
* Python
* Pandas
* Matplotlib (for visualizations)
* Jupyter Notebook
