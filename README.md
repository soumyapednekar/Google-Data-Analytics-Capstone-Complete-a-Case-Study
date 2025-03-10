These questions will guide your analysis: 
1.  What are some trends in smart device usage?
		smart rings, bracelet, necklace and watches.
2.  How could these trends apply to Bellabeat customers?
		Bellabeat is a company that produces  health-focused smart products. These products are collecting data on  activity, sleep, stress, and reproductive health has allowed Bellabeat to empower women with knowledge about their own health and habits. Since women love jewellary these are a perfect one to style for any events that help them track their body changes and fitness.
3. How could these trends help influence Bellabeat marketing strategy?
		These  trends could help build new products to keep in the competing the market.
## Business Task
1. Analyzing smart device fitness data could help unlock new growth opportunities for the company.
2. Focus on one of Bellabeat’s products and analyze smart device data to gain insight into how consumers are using their smart devices.
3. The insights you discover will then help guide marketing strategy for the company.

## Data description
Kaggle

# ASK
1. A clear summary of the business task
	Bellabeat, a **health-focused smart device company**, aims to expand its presence in the **global smart device market**. The company wants to leverage **smart fitness tracker data** to gain insights into **consumer behavior, fitness trends, and device usage patterns**.

	As a **junior data analyst**, my task is to analyze publicly available **Fitbit fitness tracker data** to uncover trends in **daily activity, sleep, stress, and health habits**. These insights will help **optimize Bellabeat’s marketing strategy** and guide product improvements.
	
	The final deliverable will include **data-driven recommendations** on how Bellabeat can align its **products, engagement strategies, and marketing efforts** with consumer behavior trends to drive growth. 

	## Problem Statement:
	Bellabeat aims to expand its market presence by analyzing **smart device usage trends** from Fitbit data. The goal is to understand **user behavior in activity, sleep, and wellness tracking** to optimize **marketing strategies** and **product development**.
	
	## How Insights Drive Business Decisions:

	- **Personalized Marketing** – Tailor campaigns based on user fitness and sleep patterns.
	- **Product Improvements** – Enhance features based on most-used health metrics.
	- **Competitive Edge** – Identify market gaps and introduce AI-driven insights.
	- **Customer Engagement** – Increase app usage through rewards and personalized recommendations.

		**Goal:** Leverage data-driven insights to enhance **Bellabeat’s growth, customer engagement, and brand positioning**.
# Prepare
Data Considerations & Evaluation
### 1. Where is your data stored?
The data is stored in **CSV format**, sourced from the **Fitbit Fitness Tracker dataset on Kaggle** (public domain). It has been uploaded and processed in **RStudio** for analysis.
### 2. How is the data organized? (Long or Wide Format?)

The dataset is primarily in wide format, where each row represents a single day or event for a user, with multiple columns for different variables (e.g., steps, calories, sleep).
Some datasets (e.g., heart rate, minute-by-minute activity) follow a long format with repeated entries for the same user at different timestamps.

### 3.  Are there issues with bias or credibility in this data? Does your data ROCCC?

Using the ROCCC framework (Reliability, Originality, Comprehensiveness, Currentness, Cited Sources):

Reliability: Data is limited to 30 Fitbit users, which may not represent the broader population.
Originality: Public dataset, not proprietary Bellabeat data.
Comprehensiveness: Only includes basic activity and sleep metrics, missing stress and hydration data.
Currentness: The dataset may not reflect recent fitness trends.
Cited Sources: Public domain (Kaggle), lacks official validation from Fitbit or Bellabeat.

### 4. How are you addressing licensing, privacy, security, and accessibility?

The dataset is CC0 (Public Domain), ensuring no privacy violations.
No personally identifiable information (PII) is included, maintaining data security.
The data is stored in CSV format, making it easily accessible for analysis.

### 5. How did you verify the data’s integrity?

Checked for missing values, duplicates, and inconsistencies.
Standardized date formats across datasets.
Validated data types (numeric values for steps, calories, timestamps for activity).

### 6. How does it help you answer your question?

Provides insights into user activity, sleep patterns, and calorie expenditure.
Helps Bellabeat understand device usage trends and optimize marketing strategies.
Supports data-driven product recommendations for better user engagement.

### 7. Are there any problems with the data?

Small sample size (30 users) limits generalizability.
Potential tracking inaccuracies in fitness data.
Lack of demographic details prevents targeted marketing insights.


The dataset provides valuable fitness tracking trends but has limitations in sample size and scope. Insights from this data can still help guide Bellabeat’s marketing and product strategies effectively. 

# Process
	## Data Processing Steps

What tools are you choosing and why?
    
    RStudio & Tidyverse: Used for data wrangling (dplyr, tidyr) and analysis.
    Lubridate: Handles date/time transformations.
    Janitor: Cleans column names for consistency.
    ggplot2: Used for visualization.
    
Have you ensured your data’s integrity?
    
    Checked for missing values, duplicate entries, and inconsistencies.
    Verified data types (dates, numeric values, categorical variables).
    Ensured timestamps are chronologically ordered.
    
What steps have you taken to ensure that your data is clean?
    
    Removed duplicates to prevent redundancy.
    Standardized column names using clean_names().
    Converted date columns to the correct format using as_date() or mdy().
    Checked for outliers (e.g., extremely high step counts).
    
How can you verify that your data is clean and ready to analyze?
    
    Used summary() and str() to confirm data types and missing values.
    Visualized data distributions (e.g., steps, sleep duration) to check anomalies.
    
Have you documented your cleaning process?
    
    Yes, through code comments and structured R scripts for reproducibility.

# Analyze

![image](https://github.com/user-attachments/assets/ce0d656f-6afb-42af-996c-44e356dc157b)

The scatter plot shows a **positive correlation** between total steps taken and calories burned, indicating that higher physical activity generally leads to greater calorie expenditure. However, the trend line suggests a **nonlinear relationship**, where calorie burn increases rapidly at first but plateaus at higher step counts. Some **outliers** exist, particularly for extremely high step counts, where calorie expenditure varies. This insight can help Bellabeat personalize fitness recommendations by setting optimal step goals for effective calorie burning.


![image](https://github.com/user-attachments/assets/3108eaf4-8613-4fba-9ee8-fdeacd5b5535)

image is a **bar chart visualizing daily step averages by weekday**. The bars represent the mean steps per day, with a **horizontal line indicating the overall average**. The graph reinforces that **Tuesday and Saturday have the highest step counts**, while **Sunday shows the lowest activity**. This insight can help Bellabeat tailor recommendations, such as **encouraging weekend activity** to maintain consistency.


![image](https://github.com/user-attachments/assets/3de4237b-26af-4da8-81c5-da98f70babca)

The bar chart **"Minutes Asleep per Weekday"** visualizes the average sleep duration across different days of the week. The data shows that **Sunday and Wednesday have the highest average sleep duration**, while **Tuesday and Thursday have slightly lower sleep times**. The horizontal line represents the overall average sleep duration. This suggests that sleep patterns are fairly consistent, with a slight increase in sleep time on weekends.



![image](https://github.com/user-attachments/assets/e2fa3331-34a3-46bf-af03-b79d4ae61dc2)
#### **Correlation Heatmap**

- This **correlation matrix** visualizes the relationships between **Total Steps, Total Minutes Asleep, Calories, and Sedentary Minutes**.
- **Key Observations:**
    - **Total Steps and Calories** show a **strong positive correlation (0.41)**, indicating that more steps generally lead to higher calorie burn.
    - **Sedentary Minutes and Calories** have a **moderate negative correlation (-0.6)**, suggesting that more sedentary time is linked to lower calorie burn.
    - **Total Minutes Asleep and Calories** have a **weak negative correlation (-0.03)**, showing that sleep duration does not strongly impact calorie expenditure.

![image](https://github.com/user-attachments/assets/765eae3a-f6e6-46fc-a8c5-7861eacfc735)
#### **Sleep Duration vs. Calories Burned**

- This scatter plot examines the relationship between **Total Minutes Asleep and Calories Burned**.
- The **correlation is weak (-0.03)**, meaning **sleep duration has little impact on calorie expenditure**.
- The red regression line is nearly **flat**, indicating **no strong trend** between sleeping more and burning more/less calories.

![image](https://github.com/user-attachments/assets/7d112b03-ff11-4d28-9114-51329bef369f)

#### **Total Steps vs. Calories Burned**

- This scatter plot examines the relationship between **Total Steps and Calories Burned**.
- The **correlation is positive (0.41)**, meaning **more steps generally lead to more calories burned**.
- The red regression line **slopes upward**, reinforcing that higher step counts are associated with higher calorie expenditure.


![image](https://github.com/user-attachments/assets/b9e7e31e-f53a-4cc7-bf4b-f353776b06b2)

### **Sedentary Time vs. Calories Burned**

- This scatter plot examines the relationship between **Sedentary Minutes and Calories Burned**.
- The **correlation appears weak** with a **slight positive trend**, as shown by the red regression line.
- Contrary to expectations, **higher sedentary time does not strongly reduce calorie burn**.
- Some individuals with **high sedentary minutes still burn significant calories**, likely due to high-intensity workouts outside of sedentary periods.


### **Few marketing suggestions for the company based on the findings**
- Emphasize Bellabeat as a holistic wellness companion that integrates activity, sleep, and wellness tracking.
- Highlight the strong positive link between step counts and calorie burn to motivate users toward increased daily movement.
- Market sleep-tracking features for improving wellness and energy recovery, rather than directly for calorie management.
- Encourage short, intense activity sessions to offset sedentary periods, particularly targeting sedentary working professionals.
- Develop personalized messaging targeting fitness enthusiasts, wellness-oriented users, and sedentary professionals separately.
- Introduce AI-powered insights and personalized recommendations to enhance user engagement.
- Gamify the user experience with step challenges, daily goal reminders, and rewards to motivate consistent activity.
- Promote Bellabeat devices as fashionable health accessories appealing specifically to style-conscious users.
- Partner with influencers in health and fitness communities to showcase real-life product benefits.
- Schedule targeted campaigns around higher activity days (Tuesdays, Saturdays) and promote recovery-focused messaging on Sundays to align with natural user trends.
