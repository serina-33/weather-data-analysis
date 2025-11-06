🌦️ Weather Data Analysis & Visualization 

📘 About the Project

This project analyzes monthly weather data such as temperature, rainfall, and humidity, and visualizes patterns using Matplotlib and Pandas.
The goal is to understand how weather changes over the year and to communicate insights through clean visualizations.

🧠 Objectives

Learn to load, clean, and analyze weather data

Create multiple charts (line, bar, and pie)

Summarize insights based on visual trends

Practice combining code + visuals + storytelling

🧰 Technologies Used

Python

Pandas (data handling)

Matplotlib (visualization)

 Google Colab

📂 Dataset

Here’s an example few sample dataset used in the project:

Month 	Avg_Temperature (°C)	 Rainfall (mm)	 Humidity (%)

Jan	         15              	    120	           75

Feb	         17	                  100	           70

Mar	         22	                   80           	65

Apr          28	                   40	            55

May	         33	                   20	            50



💻 Code Examples

1️⃣ Importing Libraries & Creating the DataFrame

import pandas as pd
import matplotlib.pyplot as plt

# Create a simple dataset

data = {
    'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 
              'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
    'Avg_Temperature': [15, 17, 22, 28, 33, 36, 35, 34, 30, 25, 20, 16],
    'Rainfall_mm': [120, 100, 80, 40, 20, 10, 5, 10, 30, 60, 90, 110],
    'Humidity_%': [75, 70, 65, 55, 50, 45, 40, 45, 55, 65, 70, 75]
}

df = pd.DataFrame(data)

print(df.head())


Output:

  Month  Avg_Temperature  Rainfall_mm  Humidity_%
0   Jan               15          120          75
1   Feb               17          100          70
2   Mar               22           80          65
3   Apr               28           40          55
4   May               33           20          50


2️⃣ Line Chart — Temperature Trend

plt.figure(figsize=(8,5))

plt.plot(df['Month'], df['Avg_Temperature'], marker='o', color='orange')

plt.title('Average Monthly Temperature')

plt.xlabel('Month')

plt.ylabel('Temperature (°C)')

plt.grid(True)

plt.show()


Insight:

* Temperature rises steadily from January to June, peaking at 36°C, then cools gradually toward December.

* Suggests a summer peak and winter dip typical of tropical or semi-arid climates.

3️⃣ Bar Chart — Monthly Rainfall

plt.figure(figsize=(8,5))

plt.bar(df['Month'], df['Rainfall_mm'], color='skyblue')

plt.title('Monthly Rainfall (mm)')

plt.xlabel('Month')

plt.ylabel('Rainfall (mm)')

plt.show()


Insight:

* The rainiest months are January and December, showing a monsoon or wet season at the start and end of the year.

* June–August are driest months with rainfall below 10 mm.

4️⃣ Pie Chart — Humidity Distribution

plt.figure(figsize=(6,6))

plt.pie(df['Humidity_%'], labels=df['Month'], autopct='%1.1f%%', startangle=90)

plt.title('Humidity Distribution by Month')

plt.show()


Insight:

* Humidity is highest during winter and lowest during summer, possibly due to dry winds or high heat evaporation.

5️⃣ Summary Report with Insights

print("🌦️ WEATHER DATA ANALYSIS REPORT 🌦️\n")

print(f"1️⃣ The hottest month is: {df.loc[df['Avg_Temperature'].idxmax(), 'Month']} ({df['Avg_Temperature'].max()}°C)")

print(f"2️⃣ The rainiest month is: {df.loc[df['Rainfall_mm'].idxmax(), 'Month']} ({df['Rainfall_mm'].max()} mm)")

print(f"3️⃣ The most humid month is: {df.loc[df['Humidity_%'].idxmax(), 'Month']} ({df['Humidity_%'].max()}%)")


Output:

🌦️ WEATHER DATA ANALYSIS REPORT 🌦️

1️⃣ The hottest month is: Jun (36°C)
2️⃣ The rainiest month is: Jan (120 mm)
3️⃣ The most humid month is: Jan (75%)

📊 Overall Insights

Parameter	Key Observation	Explanation
* Temperature	Peaks in June (36°C)	Summer season
* Rainfall	Max in January (120 mm)	Start of monsoon
* Humidity	Highest in Jan–Dec	Moist conditions during rainy season
* Dry Period	May–August	Hot and dry weather
* Pattern	Inverse relationship between rainfall & temperature	Typical tropical trend

🧩 Conclusion

This project demonstrates how to:

Load and analyze small datasets using Pandas

Visualize trends with Matplotlib

Draw meaningful conclusions from charts
It’s a perfect beginner project to understand how data can tell stories visually 🌤️📈
