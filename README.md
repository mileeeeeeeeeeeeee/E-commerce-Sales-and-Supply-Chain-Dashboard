# E-commerce-Sales-and-Supply-Chain-Dashboard

## Background
The digital era has completely changed the way people buy and sell products. Over the past decade, online shopping has become part of everyday life, drivig the rapid rise of various e-commerce platforms. This shift not only influences how consumer behave but also reshape how businesses operate

E-commerce allows business, especially B2B companies, to reach customer all around the world. However, this convenience also comes with new challenges in managing supply chain operations such as ensuring timely shipments, maintaining accurate inventory, and monitoring delivery performance. 

## Data Description
This dashboard utilizes the DataCo Supply Chain which can be accesed through this [link](https://data.mendeley.com/datasets/8gx2fvg2k6/5) or repository. The dataset contains 52 columns and 180k rows of transactional and logistic records. DataCo primarily sells three type of products clothing, sports, and electronic supplies, with product categories that may vary over time. The dataset covers transactions from January 2015 to January 2018, which also serves as the time constraint for this dashboard.

## Problem Statement
Some problems were identified from this dataset:
1. Over the three-year period, sales showed a steady decrease. In 2015, total sales were around $10.62M. Sales slightly dropped by 0.2% to $10.60M in 2016. By 2017, sales continued to fall to $10.14M, decreasing about 4.3% from the previous years.
2. Another noticeable problems is the delivery performance. Almost half of all deliveries were classified as late. This means that only around half of the shipments reached customer on time. Such condition could easily reduce customer satisfaction and eventually impact future sales.
<p align="center">
  <img width="400" height="200" alt="image" src="https://github.com/user-attachments/assets/f07ece0e-d238-4636-aeb7-888fabb32ce5" />
</p>

## Objective

## Data Understanding
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
