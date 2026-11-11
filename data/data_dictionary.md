# 📖 Data Dictionary: Flight Operations & Passenger Booking Dataset

This document details the schema, definitions, and types of attributes included in the flight operations and passenger booking dataset used in the analysis and Power BI dashboard.

| Attribute Name | Data Type | Description | Values / Examples |
| :--- | :--- | :--- | :--- |
| `num_passengers` | Integer | Total count of passengers traveling in the booking reservation | `1`, `2`, `3`, `4+` |
| `sales_channel` | Categorical | Channel / platform utilized by customer to reserve booking | `Internet`, `Mobile` |
| `trip_type` | Categorical | Classification of the flight trip itinerary | `RoundTrip`, `OneWay`, `CircleTrip` |
| `purchase_lead` | Integer | Lead time (number of days) between booking reservation and flight departure date | e.g. `262`, `112`, `7` days |
| `length_of_stay` | Integer | Total duration of stay at destination before return trip (days) | e.g. `19`, `20`, `5` days |
| `flight_hour` | Integer | Scheduled flight departure hour (24-hour military format) | `0` to `23` |
| `flight_day` | Categorical | Scheduled day of the week for flight departure | `Mon`, `Tue`, `Wed`, `Thu`, `Fri`, `Sat`, `Sun` |
| `route` | String | Origin and destination IATA airport pair for flight segment | e.g. `AKLKUL`, `DMKPER`, `PENTPE` |
| `booking_origin` | String | Country of passenger origin where ticket booking was initiated | e.g. `New Zealand`, `Australia`, `Malaysia` |
| `wants_extra_baggage` | Binary | Customer preference flag indicating additional checked baggage purchase | `1` = Yes, `0` = No |
| `wants_preferred_seat` | Binary | Customer preference flag indicating reserved / premium seat selection | `1` = Yes, `0` = No |
| `wants_in_flight_meals` | Binary | Customer preference flag indicating pre-ordered in-flight catering | `1` = Yes, `0` = No |
| `flight_duration` | Float | Scheduled flight duration in decimal hours | e.g. `5.52`, `8.83`, `4.67` hrs |
| `booking_complete` | Binary | Target indicator showing successful flight reservation and payment confirmation | `1` = Completed, `0` = Incomplete / Cancelled |
