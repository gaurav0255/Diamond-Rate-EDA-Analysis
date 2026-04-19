1. Problem Statement
The goal of this project is to analyse a diamond dataset to understand which factors influence diamond pricing and identify patterns, relationships, and key drivers that affect price.
This helps businesses:
•	Price diamonds correctly 
•	Understand customer preferences 
•	Optimize inventory and quality selection 
________________________________________
2. Dataset Description
The dataset contains 53,940 diamond records with the following features:
🔹 Numerical Features
•	carat → Weight of diamond 
•	depth → Height percentage 
•	table → Top surface width 
•	price → Target variable (in dollars) 
•	length, width, height/depth → Physical dimensions 
•	volume → Engineered feature (L × W × H) 
🔹 Categorical Features
•	cut → Quality (Fair → Ideal) 
•	colour → Grade (D → J) 
•	clarity → Purity level 
________________________________________
3. Objectives
The main objectives of this analysis are:
•	Understand distribution of variables (univariate analysis) 
•	Identify relationships between features and price 
•	Detect outliers and anomalies 
•	Perform multivariate analysis for deeper insights 
•	Discover key drivers of diamond price 
•	Provide business insights for decision-making 
________________________________________
4. Steps Involved
Step 1: Data Understanding
•	Checked shape → 53,940 rows × 11 columns 
•	Verified data types using .info() 
•	Identified categorical and numerical columns 
________________________________________
Step 2: Data Cleaning
•	Removed unnecessary column (Unnamed: 0) 
•	Renamed columns for clarity (x → length, etc.) 
•	Checked missing values → No null values 
•	Removed invalid data: 
o	Diamonds with zero dimensions 
•	Removed 145 duplicate rows 
•	Created new feature: 
o	Volume = length × width × height 
________________________________________
Step 3: Univariate Analysis
Used histograms + KDE plots
Key Insights:
•	Carat & Price → Highly right-skewed 
•	Depth & Table → Very consistent (industry standards) 
•	Length → Multimodal distribution 
•	Volume → Wide variation (captures size better than carat) 
Interpretation:
•	Most diamonds are small and affordable 
•	Few diamonds are large and expensive (long tail) 
________________________________________
 Step 4: Outlier Detection
•	Used boxplots 
•	Found outliers in: 
o	price 
o	carat 
o	dimensions 
Insight:
•	Outliers represent premium diamonds, not errors 
________________________________________
 Step 5: Bivariate Analysis
🔹 Carat vs Price
•	Strong positive correlation 
•	Price increases non-linearly 
 Bigger diamonds = exponentially higher price
________________________________________
🔹 Cut vs Price
•	Ideal & Premium → Higher median price 
•	Fair → Lowest value 
 Better cut = higher price
________________________________________
🔹 Width / Length vs Price
•	Clear positive relationship 
•	Larger size → higher price 
________________________________________
🔹 Clarity vs Price
•	Better clarity → generally higher price 
•	But variation exists due to other factors 
________________________________________
 Step 6: Multivariate Analysis
🔹 Carat + Colour + Price
•	D–F colours → Higher price at same carat 
•	G–J colours → Mid-range pricing 
Colour adds premium effect
________________________________________
 Correlation Heatmap Insights
•	Carat ↔ Price = 0.92 (very strong) 
•	Volume ↔ Price = 0.94 (strongest predictor) 
•	Dimensions highly correlated → multicollinearity present 
 Important for modelling:
•	Avoid using all size features together 
________________________________________
🔹 Advanced Scatter Analysis
•	Price increases with: 
o	Carat 
o	Size (length, width) 
o	Better colour 
•	Outliers = rare, premium diamonds 
________________________________________
5. Final Conclusions
 Key Drivers of Price:
1.	Carat (Weight) → Strongest driver 
2.	Volume (Size) → Even better predictor 
3.	Cut Quality → Impacts value perception 
4.	Colour Grade → Premium for D–F 
5.	Clarity → Secondary influence 
________________________________________
Important Insights:
•	Diamond pricing is non-linear 
•	Size-related features dominate pricing 
•	Industry follows standard proportions (depth/table) 
•	Market heavily concentrated in: 
o	Small to mid-sized diamonds 
o	Mid-range colours (G, F, E) 
________________________________________
Data Science Insight:
•	Multicollinearity exists (carat, volume, dimensions) 
•	Recommended models: 
o	Tree-based models (Random Forest, XGBoost) 
o	Feature selection for linear models 
________________________________________
 Business Insights:
•	Focus inventory on: 
o	<1.5 carat diamonds (high demand) 
•	Premium pricing strategy for: 
o	High carat + D–F colour 
•	Optimize pricing using: 
o	Volume instead of just carat

