# 🚖 Ola Ride Data Analysis using SQL and Power Bi

## 📌 Project Overview  
This project analyzes **Ola ride data** to uncover key insights about booking trends, ride cancellations, payment methods, and customer behavior. Using **SQL (MySQL Workbench)**, we performed data cleaning, aggregation, and trend analysis to provide business insights.  

## 🛠️ Technologies Used  
- **SQL (MySQL Workbench)** – Data extraction, and transformation  
- **Excel** – Data preprocessing and cleaning 
- **Power BI** – Visualization of ride trends and key metrics  

---

## 📊 Key Insights & Analysis  
✅ Identified **successful bookings and revenue trends**  
✅ Analyzed **canceled rides by customers and drivers**  
✅ Found **top 5 customers with the highest bookings**  
✅ Computed **average ride distance per vehicle type**  
✅ Extracted **payment trends and incomplete ride reasons**  

---

## 📂 Project Structure  

```
Ola-Ride-Data-Analysis/
│-- SQL/
│   ├── ola_schema.sql                 # Database and table creation
│   ├── data_cleaning.sql               # Data cleaning queries
│   ├── ride_trends.sql                 # Ride trend analysis queries
│   ├── revenue_analysis.sql            # Revenue and payment insights
│-- Excel/
│   ├── cleaned_data.xlsx               # Processed dataset for analysis
│-- PowerBI/ (Optional)
│   ├── ola_dashboard.pbix               # Power BI interactive dashboard
│-- README.md                            # Project documentation
```

---

## 🔍 SQL Queries Breakdown  
### **1️⃣ Successful Bookings**  
```sql
CREATE VIEW Successful_Bookings AS 
SELECT * FROM bookings WHERE Booking_Status = 'Success';
```

### **2️⃣ Average Ride Distance Per Vehicle Type**  
```sql
CREATE VIEW Avg_Ride_Distance AS 
SELECT Vehicle_Type, AVG(Ride_Distance) AS avg_distance 
FROM bookings GROUP BY Vehicle_Type;
```

### **3️⃣ Top 5 Customers with Most Bookings**  
```sql
CREATE VIEW Top_5_Customers AS 
SELECT Customer_ID, COUNT(Booking_ID) AS total_rides 
FROM bookings 
GROUP BY Customer_ID 
ORDER BY total_rides DESC LIMIT 5;
```

### **4️⃣ Total Booking Value of Successful Rides**  
```sql
CREATE VIEW Total_Successful_Ride_Value AS 
SELECT SUM(Booking_Value) AS total_revenue 
FROM bookings WHERE Booking_Status = 'Success';
```

*(More SQL queries can be found in the `/SQL` folder.)*  

---

## 📊 Power BI Dashboard
The **Power BI dashboard** visualizes:  
📌 **Total revenue trends** 📈  
📌 **Peak ride hours** 🕒  
📌 **Customer booking patterns** 🗺️  

### 🔹 **1️⃣ Overall View**

![Slide 1 - Overall](Slide%201.png)

---

### 🔹 **2️⃣ Vehicle Type Distribution**

![Slide 2 - Vehicle Type](Slide%202.png)

---

### 🔹 **3️⃣ Revenue by Payment Method**

![Slide 3 - Revenue by Payment Method](Slide%203.png)

---

### 🔹 **4️⃣ Cancellation Overview**

![Slide 4 - Cancellation](Slide%204.png)

---

### 🔹 **5️⃣ Customer Ratings**

![Slide 5 - Ratings](Slide%205.png)

------

## 🚀 How to Use  
1️⃣ Clone the repository:  
```bash
git clone https://github.com/sachinrawat25/Ola-Data-Analytics-Dashboard.git
```
2️⃣ Open **SQL files** in MySQL Workbench and run queries.  
3️⃣ Use **cleaned_data.xlsx** for Excel-based analysis.  
4️⃣ Open **ola_dashboard.pbix** in Power BI (if applicable).  


---

⭐ **If you found this project helpful, don’t forget to give it a star!** ⭐  
