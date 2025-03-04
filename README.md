
# **Marvel Movies Data Model: A Star Schema Approach**  

## **Introduction**  
As part of my data warehousing and analytics journey, I’ve designed a **Marvel Movies Data Model** to analyze box office performance, audience response, and character relationships efficiently. This schema follows a **star schema approach**, organizing data into **transformed tables** for optimized reporting.  

## **Data Model Overview**  
The database consists of **staging and transformed tables** that store information about Marvel movies, box office performance, audience responses, and characters. Below is a breakdown of the key tables:  

### **1. Phase (Transformed)**  
This table categorizes movies into different phases of the Marvel Cinematic Universe (MCU).  
- **phase_id** (Primary Key)  
- **phase_name**  

### **2. Marvel Movies (Transformed)**  
This fact table stores detailed information about each Marvel movie.  
- **movie_id** (Primary Key)  
- **movie_name**  
- **release_date**  
- **movie_duration**  
- **director, writer, producer**  
- **status (Released, Upcoming, etc.)**  
- **phase_id** (Foreign Key)  

### **3. Box Office Performance (Transformed)**  
This table tracks financial performance, including earnings and budget metrics.  
- **movie_id** (Primary Key, Foreign Key)  
- **movie_name**  
- **Phase_id** (Foreign Key)  
- **worldwide_box_office, domestic_box_office, international_box_office**  
- **opening_weekend, production_budget**  
- **Multiple calculated financial ratios**, including:  
  - **Budget Percentage**  
  - **Opening Weekend Gross Percentage**  
  - **International Collection Percentage**  
  - **Post-Opening vs. Budget Percentage**  

### **4. Public Response (Transformed)**  
This table captures audience and critic scores for each movie.  
- **movie_id** (Primary Key, Foreign Key)  
- **movie_name**  
- **tomato_meter (Rotten Tomatoes score)**  
- **audience_score**  
- **metacritic, cinema_score**  
- **domestic_ranking, worldwide_ranking**  
- **phase_id** (Foreign Key)  

### **5. List All Characters (Staging)**  
This staging table stores character details along with the movies they appear in.  
- **id** (Primary Key)  
- **movie_id, movie_name**  
- **character_id, character_name**  
- **Actor**  
- **phase_id**  

## **Why This Model?**  
- **Optimized for Analytics**: The data is structured in a **star schema** to support **fast querying** for BI tools.  
- **Scalable Design**: New movies, characters, and financial metrics can be added seamlessly.  
- **Supports Data Transformation**: The staging tables feed into the transformed tables, ensuring **data quality and consistency**.  

## **Conclusion**  
This Marvel Movies Data Model is designed to help analysts **track box office trends, compare audience feedback, and analyze character relationships**. With this structured approach, it’s easy to **generate insights and visualizations using tools like Power BI, Tableau, or SQL-based reporting systems**.  

What do you think about this data model? Would you add any other dimensions or fact tables? Let’s discuss in the comments! 🚀  
