# DATA-DRIVEN ANALYSIS OF A BEVERAGE RETAILER

## Overview
The project provides a comprehensive overview of a Beverage Retailer specialized in coffee, spanning from January 2019 to August 2021, offering insights into key performance indicators such as total sales, customer loyalty, sales trends over time, top-performing customers, product popularity, and geographical sales distribution.

The Beverage Retailer operates across three countries, serving a broad customer base.

The analysis was conducted using Microsoft Excel, leveraging its data analytics capabilities to visualize trends and support data-driven decision-making.

The analysis is based on an online database which can be downloaded [here](https://www.kaggle.com/datasets/mohammadkaiftahir/coffee-orders-data). <br>
The whole Excel file can be downloaded [here](Retailer_Sales_Dashboard.xlsx).

## **Table of Contents** <br>
- [Dataset](#dataset) <br>
- [Methodology](#methodology)
- [Executive Summary & Recommendations](#executive-summary--recommendations)
- [Limitations](#limitations)

## Dataset
The database has been downloaded from Kaggle, which is a popular website offering thousands of copyright-free databases.
This database consists of three sheets: “orders”, “customers”, and “products”. Please refer to the images below for more details.

+ “Orders” contains all order details, including quantity, order date, and unique customer and product IDs
+ “Customers” lists customer information such as name, email, phone number, city, address, postal code, and country
+ “products” includes the available products, with the respective coffee type, roast type, size, unit price, price per 100g, and profit

![image3](https://github.com/user-attachments/assets/f841f2de-4412-49de-82f6-d777c7dde9e0)


![image1](https://github.com/user-attachments/assets/d753771a-abb2-4122-b8cd-699e5be00ec4)


![image4](https://github.com/user-attachments/assets/be469a97-a648-4064-a262-3daad2a63e72)

The database was found to be in optimal condition, with records accurately free from any formatting inconsistencies or outliers that might skew the analysis. <br>
Given that the dataset met high standards of accuracy and consistency, there was no need for an additional data-cleaning process.

## Methodology

For this project, I followed a structured approach: data gathering, data transformation, and the creation of a dynamic, interactive dashboard using pivot tables and pivot charts.

The first issue I encountered was that columns F to M in the “orders” sheet were not populated. <br>
To address this, I filled in the missing Customer Name, Email, and Country data using the XLOOKUP function, retrieving this information from the “customers” sheet. <br>
Then, I applied the INDEX MATCH function to pull product information, such as Roast Type, Size, and Unit Price, from the “products” sheet.

For missing email addresses, I used an IF formula to replace empty values (0) with “N/A,” improving data quality and readability. The transformation is shown in the before-and-after images below.

![image5](https://github.com/user-attachments/assets/cd4b4eb4-da9f-4401-91da-5477a7748d08)

![image2](https://github.com/user-attachments/assets/9f589dcf-b685-46eb-9d2c-45d6a696c976)

To calculate values in column M “Sales”, I multiplied the unit price by the quantity sold for each row

Another necessary adjustment was standardizing the date format. Since the dataset includes both the USA and Ireland, where date formats differ (MM/DD/YYYY for the former and DD/MM/YYYY for the latter), I modified the format to include the month abbreviation to ensure clarity and consistency across all records. <br>
I made a similar adjustment to the "Size" column, which initially lacked a unit of measurement. I added “kg” as the unit, and standardized the format to one decimal place. <br>
For the "Unit Price" and "Sales" columns, I ensured all values were displayed in USD with two decimal places for accuracy. <br>

In the original dataset, both the “Coffee Type Name” and “Roast Type Name” columns contained text that was made up of the abbreviation of just three letters. <br>
To enhance clarity and simplicity, I created two new columns with the full names for each entry in the "Coffee Type" and "Roast Type" columns. <br>

Additionally, I introduced a “Loyalty Card?” column to clearly identify which customers are loyalty members. This allows for further analysis of whether loyalty members spend more or purchase more frequently than non-members. Once again, I used XLOOKUP for this process. <br>

Finally, I performed a duplicate check and confirmed that no duplicates were found. <br>

The final result of these transformations is displayed in the image below. <br>

![image7](https://github.com/user-attachments/assets/df22b563-3f8f-4731-9bf9-bec717e1d6c7)

With the data transformation complete, I proceeded to create pivot tables. The three pivot tables that I have created show the total sales by year and by coffee type, the top countries in terms of sales and the top customers by sales. 

I then developed visual representations of these tables, adjusting the design to ensure a consistent, coherent, and visually appealing dashboard, while maintaining clarity for ease of analysis.

The dashboard contains the following metrics: the total sales over time, the top customers by sales, the sales by country, and the percentage of customers holding the Loyalty Card. Additionally, I integrated three slicers to enhance interactivity, allowing users to filter the data by roast type, size, and Loyalty Card membership. A date slicer was also added, enabling to filter data for a specific time period.

The card graphs of the total sales and the % of clients with the Loyalty Card are static, while the others are dynamic. To achieve this functionality, I clicked on the timeline and the filters settings, and activated the report connection, to make sure those filters impacted the charts.

![image6](https://github.com/user-attachments/assets/ee6bcfed-3cbf-4196-9201-80485b2aedfe)

Lastly, I applied finishing touches to the dashboard by removing unnecessary gridlines, hiding the ribbons, and disabling the row and column header

## Executive Summary & Recommendations

Below are the major insights from the analysis that highlight the company's performance and suggest ways to enhance the business strategy.

+ The analysis shows that 48.7% of customers hold a Loyalty Card, reflecting strong customer engagement. This high percentage highlights the importance of nurturing this loyal customer base. To further capitalize on this, the Marketing Department should consider offering exclusive discounts and promotions to loyalty cardholders, ensuring sustained patronage. Additionally, leveraging the available customer emails can further reinforce engagement and retention, by offering loyalty programs with exclusive benefits and rewards.
+ There isn’t a strong difference between the four different types of coffee types. Arabica, Excelsa and Liberica are all nearly similar in terms of sales, while Robusta is slightly behind. There is potential to grow Arabica sales by promoting its unique qualities.  It's known for its delicate flavor profile, with notes of fruit, chocolate, and nuts. It's often considered the premium coffee bean, resulting in a higher price compared to other varieties, and this could be an important asset to consider. I recommend positioning Arabica as a premium product and exploring bundled deals or promotions to boost sales, while maximizing the success of Excelsa and Robusta, which have solid demand.
+ The US alone accounts for 79% of the sales, indicating a strong domestic market. Perhaps it would be easier to maintain the US base while continuing the expansion overseas in Ireland and the UK, as well as to tap into new markets. Canada, Australia, and New Zealand would be the most likely next countries as they are English-speaking countries and they are culturally, socially, and economically similar to the markets where the firm is already present.
+ Sales have fluctuated over time, with spikes in April 2019 and February 2020, while sales dropped during some months, particularly in August 2020. More in-depth analysis are needed for those relevant fluctuations, and figure out if, for example promotions or seasonal menus can help reverse this trend. In 2021, with an increase of more than 10% compared to the previous year, the sales were at the highest. Although sales in 2021 increased by over 10% compared to the previous year, the figures for 2022 (up to August) indicate a potential decline. This trend calls for immediate action to reverse the downturn.
+ Allis Wilmore ranks as the top customer by sales. The top customers provide significant revenue, but there's not a huge disparity between them, suggesting a fairly even sales distribution. The main opportunity is to build loyalty programs or offer personalized promotions for these customers, as it could help maintain their engagement and eventually increase sales.

![image10](https://github.com/user-attachments/assets/d1e08909-d6ea-43ae-a88d-3143a121ad2d)

## Limitations

While the analysis provides valuable insights, there are a few limitations to consider that might impact the effectiveness of the recommendations.

+ Although customer loyalty is analyzed, there is no deep segmentation of customers based on other demographics, preferences, or buying behaviors. This might limit the ability to personalize marketing strategies or identify niche customer segments.
+ The available data predominantly emphasizes sales figures and order data, yet it falls short in capturing critical insights related to customer satisfaction, such as feedback, reviews, or overall satisfaction levels. Without integrating these customer-centric metrics into the analysis, any recommendations made may lack the necessary context to fully address customer needs and preferences. Understanding how customers perceive the products and services is essential to formulating actionable strategies for improvement.
+ The figures included in the database do not differentiate between sit-down and takeaway orders, which could hinder the strategic planning. To maximize results, a tailored approach is essential for each order type.
