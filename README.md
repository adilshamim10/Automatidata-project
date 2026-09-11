# NYC Taxi Fare Analysis – Data Inspection & Exploratory Analysis

## Project Overview
This project examines 2017 NYC Yellow Taxi trip data on behalf of a fictional client, the New York City Taxi and Limousine Commission (NYC TLC). As an early-stage step in a larger predictive modeling engagement, the goal here is to inspect, clean-check, and explore the dataset to identify which variables are most likely to be useful in a future model predicting taxi fares.

## Business Context
NYC TLC wants to better understand the factors that drive taxi fares. Before building any predictive model, the data first needs to be inspected for structure, data types, and quality issues, and key variables need to be explored to understand their relationship to fare amount.

## Dataset
The dataset (`2017_Yellow_Taxi_Trip_Data.csv`) contains 18 columns describing individual NYC taxi trips, including:
- `trip_distance` – distance traveled per trip
- `total_amount` / `tip_amount` – fare and tip amounts
- `payment_type` – encoded payment method (credit card, cash, no charge, dispute, unknown, voided)
- `VendorID` – identifier for the taxi vendor/provider
- `passenger_count` – number of passengers per trip
- Pickup/drop-off timestamp fields

## Methods
- Performed initial data inspection (`.head()`, `.info()`, `.describe()`) to check data types, structure, and missing values
- Sorted and examined `trip_distance` and `total_amount` to identify unusual or outlier values
- Analyzed `payment_type` and `VendorID` distributions using `.value_counts()`
- Used Boolean filtering and `groupby()` to compare average tip amounts by payment type and by passenger count
- Tools used: Python, pandas, NumPy

## Key Findings
- **Data types need cleanup:** Pickup and drop-off time columns are stored as text rather than proper datetime objects, which will need to be converted before any time-based analysis or modeling.
- **Outliers exist:** Sorting by `trip_distance` and `total_amount` surfaced unusually high values at the extremes, worth flagging for review before modeling (e.g., data entry errors or genuinely rare long-distance trips).
- **Payment method affects tipping behavior:** Average tip amounts differ notably between credit card and cash payments, likely partly reflecting that cash tips aren't always recorded in the data.
- **Strongest predictive variables identified:** `trip_distance` and trip duratio
