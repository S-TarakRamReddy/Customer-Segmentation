# Demo Video Script: Customer Segmentation

**Estimated Time:** 2-3 minutes  
**Presenter:** Tarak Ram Reddy  

---

**[Scene: Presenter on screen or voiceover with the Title Slide showing "Customer Segmentation using K-Means Clustering"]**

**Presenter:** "Hello everyone! My name is Tarak Ram Reddy, and today I’ll be walking you through my submission for Task 6 of the Synent Technologies Data Science Internship: Customer Segmentation."

**[Scene: Transition to Problem Statement Slide / Notebook Header]**

**Presenter:** "The goal of this project is to help a mall understand its customer base better. When a business knows *who* is buying, they can tailor their marketing, improve customer retention, and ultimately increase revenue. To do this, we grouped customers into distinct segments based on their purchasing behavior using unsupervised machine learning."

**[Scene: Transition to the Notebook - Data Loading & Cleaning Section]**

**Presenter:** "We started with the Mall Customer dataset, which includes details like Age, Gender, Annual Income, and a proprietary Spending Score from 1 to 100. First, I performed basic data cleaning. The dataset was very clean—no missing values or duplicates—so I focused on standardizing the column names for easier access."

**[Scene: Transition to the Notebook - Exploratory Data Analysis (EDA)]**

**Presenter:** "Next, I moved into Exploratory Data Analysis. Looking at the distributions, we saw that the average customer is around 38 years old, earning about 60,000 dollars a year. But the most revealing visualization was the pairplot between Annual Income and Spending Score, where distinct clusters were naturally visible even before applying any algorithms."

**[Scene: Transition to the Notebook - Preprocessing & Choosing K]**

**Presenter:** "For modeling, I excluded the Customer ID, as it has no analytical value, and focused on Income and Spending Score. Because K-Means is a distance-based algorithm, I applied a StandardScaler to normalize the features. 

To find the optimal number of clusters, I used the Elbow Method to plot the Within-Cluster Sum of Squares, and calculated the Silhouette Scores. Both metrics clearly pointed to *K equals 5* as the optimal number of segments."

**[Scene: Transition to the Notebook - Model Building & Final Plot]**

**Presenter:** "I then trained the K-Means model with 5 clusters and visualized the results. As you can see on this scatter plot, the segments are beautifully separated:

1. **Premium Customers** in the top right—high income and high spending.
2. **Target Customers** in the top left—low income but high spending.
3. **Standard Customers** in the middle.
4. **Conservative Customers** in the bottom right—high income but low spending.
5. And **Budget Shoppers** in the bottom left."

**[Scene: Transition to Business Recommendations Slide]**

**Presenter:** "These insights translate directly to business strategy. For example, we should target our Premium customers with exclusive VIP programs and early product access. Conversely, our Conservative customers require marketing that emphasizes quality and practical value to encourage them to spend more."

**[Scene: Presenter on screen / Final Slide]**

**Presenter:** "In conclusion, this clustering model transitions our marketing strategy from a 'one-size-fits-all' approach to highly targeted, efficient campaigns. Thank you for watching, and I look forward to any feedback from the Synent Technologies team!"
