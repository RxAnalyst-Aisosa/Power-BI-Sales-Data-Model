# Model Documentation

## Overview

This Power BI project is centred on a dimensional model for sales and budget analysis.

## Tables

### `fact_sales`

Central transactional fact table. Visible fields in the model include:

- customer_id
- junk_id
- line_total
- manager_id
- order_date
- order_id
- order_line
- payment_id
- product_id
- quantity
- salesperson_id
- ship_date
- store_id

The table also contains the **Sales by Team** measure.

### `fact_budget`

Budget-oriented fact table containing:

- budget_month
- budget_quantity
- budget_sales
- product_id
- scenario

### `dim_customer`

Customer dimension containing fields such as:

- customer_id
- customer_number
- first_name
- last_name
- city
- points
- tier

### `dim_product`

Product dimension containing:

- product_id
- product_name
- category
- subcategory
- price
- sku

### `dim_store`

Store dimension containing:

- store_id
- store_name
- city
- region_id

### `dim_payment`

Payment dimension containing:

- payment_id
- payment_method
- card_type
- card_network

### `dim_date`

Calendar dimension containing:

- date
- day_name
- month_name
- month_start
- quarter
- year

### `dim_employee (role_playing dim)`

Employee dimension containing:

- id
- name
- role
- team
- email
- hire_date

This dimension is reused across employee-related roles in the model.

### `junk_dim`

Junk dimension containing:

- junk_id
- order_channel
- order_status
- promotion_code

## Modelling Features

The model demonstrates:

- fact and dimension separation
- one-to-many relationship design
- a central sales fact table
- a separate budget fact table
- conformed dimensions
- a dedicated date dimension
- a role-playing employee dimension
- a junk dimension for low-cardinality attributes
- a DAX measure for team-level sales analysis

## Purpose

The purpose of the model is to provide a cleaner analytical foundation for Power BI reporting and to demonstrate understanding of the modelling layer that sits underneath dashboards and visualisations.
