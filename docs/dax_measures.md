# 📐 Core DAX Measures Documentation

This documentation summarizes the key Data Analysis Expressions (DAX) developed in Microsoft Power BI for monitoring flight operational efficiency, on-time performance (OTP), delay factors, and passenger conversion metrics.

---

### 1. On-Time Performance (OTP) Rate
Measures the percentage of scheduled flights arriving within 15 minutes of scheduled arrival time without being cancelled.

```dax
OTP Rate = 
DIVIDE(
    CALCULATE(COUNTROWS('Fact_Flights'), 'Fact_Flights'[ArrDelayMinutes] <= 15, 'Fact_Flights'[Cancelled] = 0),
    CALCULATE(COUNTROWS('Fact_Flights'), 'Fact_Flights'[Cancelled] = 0),
    0
)
```

---

### 2. Average Departure Delay (Minutes)
Calculates the mean departure delay in minutes, filtering specifically for positive delay instances to avoid skew from early departures.

```dax
Avg Dep Delay = 
AVERAGEX(
    FILTER('Fact_Flights', 'Fact_Flights'[DepDelayMinutes] > 0),
    'Fact_Flights'[DepDelayMinutes]
)
```

---

### 3. Cancellation Rate
Computes the proportion of scheduled flights cancelled due to operational, mechanical, or meteorological constraints.

```dax
Cancellation Rate = 
DIVIDE(
    CALCULATE(COUNTROWS('Fact_Flights'), 'Fact_Flights'[Cancelled] = 1),
    COUNTROWS('Fact_Flights'),
    0
)
```

---

### 4. Booking Conversion Rate
Calculates the overall conversion rate of passenger inquiries to fully completed flight reservations.

```dax
Conversion Rate = 
DIVIDE(
    CALCULATE(COUNTROWS('Fact_Flights'), 'Fact_Flights'[booking_complete] = 1),
    COUNTROWS('Fact_Flights'),
    0
)
```

---

### 5. Ancillary Service Attachment Rate
Measures customer adoption percentage for key high-margin ancillary products (extra baggage, preferred seating, meals).

```dax
Ancillary Attachment Rate = 
DIVIDE(
    CALCULATE(
        COUNTROWS('Fact_Flights'), 
        'Fact_Flights'[wants_extra_baggage] = 1 || 
        'Fact_Flights'[wants_preferred_seat] = 1 || 
        'Fact_Flights'[wants_in_flight_meals] = 1
    ),
    COUNTROWS('Fact_Flights'),
    0
)
```
