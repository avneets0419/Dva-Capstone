# Airbnb Revenue & Occupancy Optimization Analysis

Newton School of Technology – DVA Capstone 1  
Group - 8

---



## Introduction

This capstone project analyzes Airbnb listing data to determine:

**Which neighborhoods, room types, and pricing strategies should Airbnb hosts focus on to maximize revenue and occupancy while maintaining strong demand and ratings?**

This project simulates a real-world analytics consulting assignment where structured data is transformed into actionable, decision-oriented business recommendations for Airbnb hosts.

---

## Table of Contents

- [Dataset Overview](#dataset-overview)
- [Project Objective](#project-objective)
- [Project Overview](#project-overview)
- [Data Cleaning Strategy](#data-cleaning-strategy-google-sheets)
- [KPI Framework](#kpi-framework)
- [Analytical Approach](#analytical-approach)
- [Dashboard Design](#dashboard-design)
- [Expected Business Recommendations](#expected-business-recommendations)
- [Tools Used](#tools-used)
- [Project Structure](#project-structure)
- [Contributors](#contributors)

---

## Dataset Overview

### Raw Data Columns

The dataset contains the following attributes:

| Column Name | Description | Data Type |
|-------------|------------|-----------|
| `NAME` | Listing title | Text (String) |
| `host id` | Unique host identifier | Integer |
| `host_identity_verified` | Whether host identity is verified | Boolean (True/False) |
| `host name` | Name of host | Text (String) |
| `neighbourhood group` | Major area / borough | Text (Categorical) |
| `neighbourhood` | Specific locality | Text (Categorical) |
| `lat` | Latitude | Decimal (Float) |
| `long` | Longitude | Decimal (Float) |
| `country` | Country | Text (String) |
| `country code` | Country short code | Text (String) |
| `instant_bookable` | Whether property can be instantly booked | Boolean (True/False) |
| `cancellation_policy` | Type of cancellation | Text (Categorical) |
| `room type` | Entire home / Private room / Shared room | Text (Categorical) |
| `Construction year` | Year property was built | Integer |
| `price` | Listing price | Decimal (Currency) |
| `service fee` | Platform service fee | Decimal (Currency) |
| `minimum nights` | Minimum booking nights | Integer |
| `number of reviews` | Total reviews received | Integer |
| `last review` | Date of most recent review | Date |
| `reviews per month` | Average monthly reviews | Decimal (Float) |
| `review rate number` | Rating score | Decimal (Float) |
| `calculated host listings count` | Listings managed by host | Integer |
| `availability 365` | Available days in a year | Integer |
| `house_rules` | Property rules | Text (String) |
| `licence` | Registration / license information | Text (String) |


---

## Project Objective

The project aims to analyze:

- High-performing neighborhoods  
- Best-performing room types  
- Optimal pricing ranges  
- Impact of ratings and reviews  
- Occupancy patterns  
- Host portfolio size effects  

The goal is to generate data-backed strategic recommendations.

---



## Project Overview

This capstone follows an end-to-end analytics workflow:

1. Define the business problem  
2. Clean and standardize raw data  
3. Design KPIs  
4. Perform exploratory and statistical analysis  
5. Build dashboards  
6. Deliver actionable recommendations  

---

## Data Cleaning Strategy (Google Sheets)

### Data Standardization

- Remove currency symbols from `price` and `service fee`
- Convert numeric columns properly
- Format date column (`last review`)
- Standardize room type categories

### Missing Value Handling

- Remove rows with missing `price` or `neighbourhood`
- Treat missing review scores carefully
- Handle missing `licence` values separately

### Feature Engineering (New Calculated Columns)

| New Column | Formula / Logic |
|------------|----------------|
| Occupancy Rate | `(365 - availability 365) / 365` |
| Estimated Annual Revenue | `price × (365 - availability 365)` |
| Total Cost to Guest | `price + service fee` |
| Revenue per Available Day | `price × occupancy rate` |
| Property Age | `Current Year - Construction Year` |
| Demand Score | `reviews per month × review rate number` |

---

## KPI Framework

### Revenue KPIs

- Average Price by Neighbourhood  
- Estimated Annual Revenue  
- Revenue per Listing  
- Revenue per Host  

### Occupancy KPIs

- Occupancy Rate  
- Availability Distribution  
- Instant Bookable Impact on Occupancy  

### Demand & Rating KPIs

- Average Review Score  
- Reviews per Month  
- Rating vs Price Correlation  

### Segmentation KPIs

- Room Type Performance  
- Verified vs Non-Verified Hosts  
- Cancellation Policy Impact  
- Host Portfolio Size Impact  

---

## Analytical Approach

### Neighborhood Analysis

- Compare average price  
- Compare occupancy  
- Compare revenue  
- Identify high-demand micro-markets  

### Room Type Analysis

- Entire Home vs Private Room vs Shared Room  
- Revenue comparison  
- Rating differences  
- Occupancy trade-offs  

### Pricing Strategy Analysis

Price band segmentation:

- Budget  
- Mid-Range  
- Premium  

- Revenue vs occupancy curve  
- Optimal pricing zone detection  

### Rating & Demand Correlation

- Does higher rating justify higher pricing?  
- Correlation: `review rate number` vs `price`  
- Correlation: `reviews per month` vs `occupancy`  

### Host Strategy Analysis

- Multi-listing hosts vs single listing hosts  
- Verified vs non-verified hosts  
- Cancellation policy flexibility impact  

---

## Dashboard Design

The dashboard includes:

### Executive Summary Page

- Total Listings  
- Average Price  
- Average Occupancy Rate  
- Total Estimated Revenue  

### Neighborhood Performance

- Revenue heat comparison  
- Price vs occupancy scatter  

### Room Type Breakdown

- Revenue share by room type  
- Rating comparison  

### Pricing Insights

- Price distribution  
- Revenue vs price trend  

### Host Insights

- Verified host performance  
- Listing count impact  

Primary Tool: Google Sheets  
Optional Visualization Layer: Looker Studio  

---

## Expected Business Recommendations

After analysis, the final recommendations will answer:

- Which neighborhoods show high revenue and strong occupancy  
- Which room types offer the best balance of rating and income  
- What pricing band maximizes revenue without hurting demand  
- Whether instant booking improves occupancy  
- Whether verified hosts command better ratings  
- Optimal cancellation policy for revenue stability  

---

## Tools Used

### Mandatory
- Google Sheets (Cleaning, Analysis, and Dashboarding)

### Optional
- Python (Advanced statistical validation)
- Looker Studio (Enhanced visualization layer)

---

## Project Structure

```
Airbnb-Revenue-Optimization/
│
├── Raw_dataset/
├── Cleaned_dataset/
│ └── airbnb_cleaned_sheet.csv
├── Calculation_and_pivot_table/
│ └── pivot.csv
├── Dashboards/
├── Presentation/
├── Documentation/
└── README.md
```

---

## Contributors

**Section:** B  
**Group:** G-8  

### Team Members

| Name | Enrollment Number |
|------|-------------------|
| Soumya Tiwari | 2401020111 |
| Avneet Singh | 2401010117 |
| Kushagra Bhardwaj | 2401010247 |
| Dhruv Kumar | 2401010152 |
| Alisha Gupta | 2401010057 |
| Vaibhav Singh | 2401020074 |