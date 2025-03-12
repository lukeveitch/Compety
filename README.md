# Compety
2025 Product Analytics Hackathon


# # Experiment Details

**Hypothesis**: Increasing the size of food images on restaurant menu cards will improve conversion to orders.

**Test Location**: London
**Test Duration**: 00:00, Monday, 25 November 2024 to 23:59, Saturday, 30 November 2024
**User Split**: Users were randomly assigned to either the control group (original design) or the test group (larger food
images)
**Key UI Difference**: The control group saw the original smaller images, while the test group saw larger food images (as shown in the provided screenshots)

**Dataset Overview**
reload_the_page – User updated the list of restaurants
entry_to_shop – User entered a specific restaurant
order_paid – User completed an order and made payment
order_finished – Order was finished marked with a final status (is generated for each paid order)

| **field** | **type** | **desc** |
|-----------|----------|----------|
| event_id | int | ID |
| session_id | int | ID |
| user_id | int | ID |
| variation | int | User Variation: 1- old design, 2 - new design with bigger pictures. |
| platform | string | User platform: iOS / Android |
| datetime_event | datetime | The date and time event was conducted |
| event_type | string | The name of the event |
| final_order_status | string | Order Status: Successful, Cancelled, Refunded after delivery |
| shop_id | int | ID |

### 1 - Data Cleaning & EDA
- Missing values, duplicates, unique shops and users, distributions etc...

### 2 - Calculate conversion rates 
- Restaurant view → Restaurant entry
- Restaurant entry → paid order
- Paid order → Order finished 

### 3 - Statistical Significance
- Calc. confidence intervals

### 4 - Cohort Analysis

Segment your analysis by:

- Platform (iOS vs Android)
- Time of day/day of week
- Final order status (Successful, Cancelled, Refunded)

This will help identify if the change impacts specific user segments differently.

### 5 - Interpret Results

