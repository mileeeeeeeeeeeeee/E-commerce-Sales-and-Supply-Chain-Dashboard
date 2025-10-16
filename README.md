# E-commerce-Sales-and-Supply-Chain-Dashboard

## Background
The digital era has completely changed the way people buy and sell products. Over the past decade, online shopping has become part of everyday life, drivig the rapid rise of various e-commerce platforms. This shift not only influences how consumer behave but also reshape how businesses operate

E-commerce allows business, especially B2B companies, to reach customer all around the world. However, this convenience also comes with new challenges in managing supply chain operations such as ensuring timely shipments, maintaining accurate inventory, and monitoring delivery performance. 

## Data Description
This dashboard utilizes the DataCo Supply Chain which can be accesed through this [link](https://data.mendeley.com/datasets/8gx2fvg2k6/5) or repository. The dataset contains 52 columns and 180k rows of transactional and logistic records. DataCo primarily sells three type of products clothing, sports, and electronic supplies, with product categories that may vary over time. The dataset covers transactions from January 2015 to January 2018, which also serves as the time constraint for this dashboard.

## Problem Statement
Some problems were identified from this dataset:
1. **Over the three-year period, sales showed a steady decrease**. In 2015, total sales were around $10.62M. Sales slightly dropped by 0.2% to $10.60M in 2016. By 2017, sales continued to fall to $10.14M, decreasing about 4.3% from the previous years.
2. Another noticeable problems is the delivery performance. **Almost half of all deliveries were classified as late**. This means that only around half of the shipments reached customer on time. Such condition could easily reduce customer satisfaction and eventually impact future sales.
<p align="center">
  <img width="400" height="200" alt="image" src="https://github.com/user-attachments/assets/f07ece0e-d238-4636-aeb7-888fabb32ce5" />
</p>

## Objective
Based on the problems above, the dashboard will be created to help the Supply Chain Management tracks how sales, profit, and delivery performance evolve over time. Through this dashboard, the team can quickly **spot inefficiencies in e-commerce performance, monitor key metrics, and plan improvements that lead to more efficient and reliable operations.**

## Building the Dashboard 
### Data Understanding
The dashboard focuses on analyzing Key Performance Indicator (KPI) and Logistic Indicator. Therefore, the main columns used in the analysis are listed below:
- Sales per customer: Total sales value per customer
- Benefit per order: Total profit generated from each order placed
- Delivery Status: The delivery status of order is categorized into "Advance shipping", "Late delivery", "Shipping canceled", "Shipping on time"
- Customer State: State or region of the customer (B2B)
- Department name: Department name of the store
- Order date: Date when the order was placed
- Order Item Profit Ratio: Profit margin ration per order item
- Order Id: Unique identifier for each order
- Customer Id: Unique identifier for each customer
- Market: Region where the order is delivered
- Shipping date: Date when the order was shipped
- Days for shipping (real): Actual number of days taken for delivery
- Days for shipment (scheduled): Expected number of days taken for delivery
- Category name: Category of the purchased product
- Customer Segment: Type of consumer is categorized into Consumer, Corporate, Home Office
- Order Item Quantity: Item quantity per product of each order

### Data Cleaning
The goal of the data cleaning process was to change the raw data into a format that could be more easily analyzed. This stage involved ajusting several data types and creating additional columns. All of this stages were done in Power BI.
- Data type adjustments:
  - Sales and Benefit columns were converted into decimal number format.
  - Order Date and Shipping Date (originally in U.S. date format 'mm/dd/yyyy') were converted to global date and time format 'dd/mm/yyyy'.
  - Numerical columns such as Order Item Quantity, Days for Shipping (Real), and Days for Shipment (Scheduled) were converted to whole number format.
- Additional column creation:
  To simplify sorting in Delivery Status column, an additional column named Delivery Status Order was created based on earliest into latest status.
  - Advance Shipping = 1,
  - Shipping On Time = 2,
  - Late Delivery = 3,
  - Shipping Canceled = 4
This transformation ensured the dataset is consistent, structured, and ready for further analysis in the dashboard.

### Creating Metrics
Key Performance Indicator should show a comparison between current period and the previous period to determine whether the performance is improving or declining. Therefore, it is necesarry to build several measures for the KPIS, such as those for the current period, the prevuous period, and the difference between the two. One example for the sales measure is shown below. For the KPI, loss measures for Sales and Orders were also created. These measures resprent the potential sales and orders that could have generated revenue but did not.

<p align="center">
  <img width="278" height="337" alt="image" src="https://github.com/user-attachments/assets/a341329e-3229-436f-948d-50e9a5c05748" />
<p/>

Another issue identified was related to delivery time. To address this, Reorder Point (ROP) and Safety Stock (SS) analyses were used to explore possible solutions.
For an e-commerce business, one of the key advantages lies in providing instant or faster delivery. To maintain this advantage, the company needs to analyze its ROP to improve delivery performance, as the data indicates that most shipments were delivered late.  When inventory reaches ROP, e-commerce or business should order new inventory to keep up with the daily demand and service level. ROP was calculated by the formula below. [1]

<p align="center">
  <img width="350" height="80" alt="image" src="https://github.com/user-attachments/assets/88ae76fc-fbe3-4bd7-ab75-8e6d2c7e2256" />
<p/>

In this formula, the variables include daily sales velocity (daily demand), lead time in days, and safety stock. Daily sales were calculated using _Order Item Quantity_ for each days, while lead time was represented by average of _Days for shipping (real)_. For safety stock, another common formula is used [2]. This formula also incorporates lead time and demand for each product. The value Z represents the service level, which in this case is 95%, corresponding to a Z-score of 1.65 from the normal distribution.

<p align="center">
  <img width="300" height="78" alt="image" src="https://github.com/user-attachments/assets/e782a927-8e83-421e-a8d3-19bbc5627b0b" />
<p/>

### Outlining The Dashboard
After creating the metrics, the next step is outlining the dashboard.

## Answering the Problem


Source: 
[1] https://www.netsuite.com/portal/resource/articles/inventory-management/reorder-point-rop.shtml
[2] https://web.mit.edu/2.810/www/files/readings/King_SafetyStock.pdf
