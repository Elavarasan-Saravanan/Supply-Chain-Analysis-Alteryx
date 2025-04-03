# Alteryx

# Supply Chain Analysis Project

## Tools Used:
- Alteryx

## Dataset Used:
Supply chain dataset covering warehouses and retail stores in Tamil Nadu.

## Business Problem:
Efficient supply chain management is critical for minimizing costs, reducing delays, and ensuring optimal stock levels. This project analyzes product movements, delivery performance, and demand forecasting to identify bottlenecks and optimize logistics operations.

## Approach to Solving the Problem:
This project was implemented using **Alteryx**, where a workflow was designed to clean, transform, and analyze supply chain data. Key supply chain metrics were extracted using various Alteryx tools to generate actionable insights.

## Alteryx Workflow Steps:

**Workflow:** ![image](https://github.com/user-attachments/assets/99cf48fc-61e1-43b7-96a8-388335114bd1)


### 1. **Data Input and Cleaning**

- **Used Input Tool** to load the supply chain dataset.
- **Data Cleansing Tool** to remove null values and inconsistencies.
- **Unique Tool** applied to the `Order ID` column to ensure unique transactions.

### 2. **Data Transformation and Filtering**
- **Select Tool** used to correct the data types for accurate processing.
- **Filter Tool** applied to remove rows where `[Quantity] > 0`, ensuring valid transactions.
- **Filter Tool** applied to keep only reasonable cost values (`[Cost_INR] >= 1 AND [Cost_INR] <= 5000`).
- **Filter Tool** applied to allow only reasonable delivery days (`[Delivery_Time_Days] >= 1 AND [Delivery_Time_Days] <= 10`).

### 3. **Geospatial Analysis (Mapping Warehouses & Stores)**
- **Create Points Tool** used to map warehouse locations using `Longitude` and `Latitude`.
- **Browse Tool** used to visualize the warehouse locations on a map.
- **Create Points Tool** applied to map store locations with `Longitude` and `Latitude`.
- **Browse Tool** used to view store locations on the map.

### 4. **Distance Calculation & Performance Metrics**
- **Distance Tool** applied to calculate the distance from each warehouse to stores.
- **Summarize Tool** used to compute:
  - **Average Delivery Time (Days)**
  - **Average Distance (Km)**
  - **Total Orders Count**
  - **Sum of Delayed Orders** 
- **Select Tool** applied to sort the data by `Avg_Distance (Km)` in ascending order.
- **Formula Tool** used to create new calculated columns:

  
  ![image](https://github.com/user-attachments/assets/46fb8d34-4be1-4cff-ba1b-1c4caee490e9)

  - `Delayed Percentage = (Delayed Orders / Total Orders) * 100`
  - `Performance Category` based on delivery efficiency 

### 5. **Output Export**
- **Output Tool** used to export the final cleaned and processed dataset for further analysis.

## Conclusion:
By analyzing supply chain data with Alteryx, this project provides valuable insights into logistics optimization, cost reduction, and inventory management. The insights generated can help businesses improve supply chain efficiency and reduce operational costs.

