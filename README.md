Airbnb Data Cleaning & Analysis Project

📋 Project Overview:

Comprehensive cleaning and analysis of 86,186 Airbnb listings to build accurate price prediction models, uncovering key pricing drivers and optimal modeling strategies.

✅ Key Tasks Performed:
Data cleaning and visualization in AirBnB_DataCleaning.ipynp
linear and other models implementations in LB_AirBnB.ipynp 

1. Data Cleaning & Preparation

Missing Value Treatment: Imputed price (6.29% missing), reply time (22.42%), dropped consumer (58.90% missing)
Outlier Management: Capped prices at 99th percentile ($1,296.45), removing extreme outliers up to $20,000
Data Type Correction: Fixed European decimal formats (comma → dot), converted percentage strings to numeric
Duplicate Removal: Eliminated 5,144 duplicate listings
2. Feature Engineering

Created impactful features: is_spacious (2+ beds & 2+ baths), host_reliability score
Developed smart ratios: beds_per_guest, person_per_room
Engineered interaction terms: accommodates × bathrooms, city × property_size
3. Model Development & Comparison

7 Models Tested: Linear Regression, Ridge/Lasso, Random Forest, Gradient Boosting, HistGB, KNN, SVM
Performance Ranking: HistGB (R²=0.630) → Random Forest (0.614) → Gradient Boost (0.567) → Linear (0.475) → KNN (0.495) → SVM (0.390)
Key Finding: Tree-based models outperform linear methods by 25-32%
4. Critical Insights Discovered

Top Price Driver: Property spaciousness (21.5% importance) - 2+ bedrooms AND 2+ bathrooms
Location Premiums: Singapore (+$162), Sydney (+$50) vs Berlin (-$120 discount)
Surprising Result: Host response metrics have minimal pricing impact
Optimal Strategy: Capping outliers improved model performance by 4.8%
5. Deliverables Generated

Cleaned dataset: Airbnb_nocap_price.csv (81,042 listings, 15 features)
Production-ready model: Hist Gradient Boosting with 63% variance explained
Business recommendations for pricing optimization and property positioning
Impact: Transformed raw, messy data into actionable insights with 63% predictable pricing accuracy, enabling data-driven Airbnb hosting strategies.


Airbnb Price Analysis: Summary & Findings 

Implementation: 

Cleaned 86K+ Airbnb listings (price, bathrooms, location data) 
Performed extensive data cleaning & outlier removal 
Engineered smart features (is_spacious, host_reliability, etc.) 
Tested 7+ models (Linear, Ridge, Lasso, Random Forest, Gradient Boosting) 
Used cross-validation & feature importance analysis 
Key Findings: 

1. Model Performance: 

Best Model: Hist Gradient Boosting (R² = 0.629 - 63% variance explained) 
Random Forest: R² = 0.615 (61%) 
Linear Regression: R² = 0.475 (48%) 
Tree models outperform linear models by 25-32% 
Impact of Capping Outliers: 

Without Capping (Raw Data): 

HistGB R²: 0.6010 (60% variance explained) 
Linear R²: 0.4639 (46%) 
SVM R²: 0.4540 (45%) 
With Capping (99th percentile): 

HistGB R²: 0.6301 (63% variance) → +4.8% improvement 
Linear R²: 0.4753 (48%) → +2.5% improvement 
SVM R²: 0.3895 (39%) → -14.2% worse 
🔍 Key Insights: 

Tree models improve with capping (+4.8% for HistGB) 
Linear models improve slightly (+2.5%) 
SVM performs worse with capping (-14.2%) 
KNN improves from 0.4681 to 0.4950 (+5.7%) 
Conclusion: Capping outliers at 99th percentile improves tree model performance while potentially hurting distance-based methods like SVM.  

Capping outliers improved overall model performance, particularly for tree-based algorithms 

 

2. Top Price Drivers: 

Property Size: Accommodates (+$63/guest), Bathrooms (+$51), Bedrooms (+$27) 
Location Premium: Singapore (+$162), Sydney (+$50), Berlin (-$120 discount) 
Spaciousness: 2+ bedrooms AND 2+ bathrooms = 21.5% importance (top feature!) 
Host Reputation: Review count, multiple listings, high acceptance rates 
3. Surprising Insights: 

Host response time/rate has minimal impact on price 
Guest favourite flag has negative predictive power 
Asian cities generally offer discounts vs Western markets 
Property features matter more than host metrics 
4. Data Issues Discovered: 

Price data had extreme outliers ($20M listings!) 
European decimal formatting caused conversion errors 
Missing values in key columns required smart imputation 
Business Recommendations: 

Focus on property size over host perfection metrics 
Market spacious listings (2+2) as premium category 
Price strategically by city: Premium for Singapore/Sydney, discounts for Berlin/Tokyo 
Use HistGB model for price predictions (±$120 accuracy) 
Technical Learnings: 

Tree-based models handle Airbnb's non-linear pricing best 
Feature engineering (is_spacious) beats complex interactions 
Regularization unnecessary - features are already clean 
KNN/SVM underperform significantly for this dataset 
Final Takeaway: Airbnb pricing is 63% predictable using basic listing data, with property size and location as dominant factors. 

 
