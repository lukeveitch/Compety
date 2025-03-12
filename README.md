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
- [] 1. Check for Data Completeness

Verify that events are properly logged for the entire test period (Nov 25-30, 2024)
Ensure no gaps in data collection for either variation
Look for any periods of technical issues that might have affected data collection

- [ ] 2. Validate User Assignment

Confirm that users were properly randomized between control and test groups
Check if the distribution between variations is roughly equal (should be close to 50/50)
Verify that users stayed in their assigned variation throughout the test period

- [ ] 3. Identify and Handle Outliers

Look for unusual user behavior patterns (e.g., users with extremely high numbers of page reloads)
Identify and potentially exclude test accounts or internal team members
Flag sessions with technical errors that might affect normal user behavior

- [ ] 4. Session and User Data Consistency

Check for broken sessions (incomplete funnel data)
Ensure each session is properly associated with the correct user_id
Validate that the platform information (iOS/Android) is consistent within sessions

- [ ] 5. Event Sequence Validation

Verify the logical order of events (e.g., a user can't have order_paid without entry_to_shop)
Look for duplicate events within the same session
Check for proper timestamps and chronological order of events

- [x] 6. Handle Missing Values

Identify any null values in critical fields
Determine appropriate strategies for missing data (e.g., exclusion or imputation)
Check if missing values are distributed equally between test and control groups

- [] 7. Platform-Specific Issues

Check if data collection works properly across both iOS and Android
Look for platform-specific anomalies that might indicate technical issues

- [] 8. Create Analysis-Ready Dataset

Create a clean dataset that includes only valid sessions and events
Generate derived metrics for analysis (conversion rates, time between events, etc.)
Segment users appropriately for cohort analysis

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

