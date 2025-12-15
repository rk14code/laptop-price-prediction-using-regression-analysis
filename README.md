# 💻 Laptop Price Prediction Using Regression Analysis 
## 📌 Project Overview

This project applies **machine learning regression techniques** to predict laptop prices based on hardware specifications, brand value, and display characteristics.
The goal is to help consumers, retailers, and manufacturers make data-driven pricing decisions by understanding how different components influence laptop cost.

Through **exploratory data analysis (EDA)**, **feature engineering**, **model tuning**, and **robust evaluation**, the project uncovers key pricing drivers such as **brand name**, **RAM size**, **processor type**, **storage configuration**, **display quality (PPI)**, **GPU brand**, and **laptop weight.**
_____
## 📊 Dataset Description
Each row represents a laptop model with its technical configuration and final selling price in INR.​

**Company** → Laptop brand (Apple, Dell, HP, Lenovo, Asus, MSI, etc.)​

**TypeName** → Category/type (Notebook, Gaming, Ultrabook, 2 in 1 Convertible, Workstation, Netbook)​

**Inches** → Screen size in inches (e.g., 13.3, 14.0, 15.6, 17.3)​

**ScreenResolution** → Resolution string (e.g., Full HD 1920x1080, IPS Panel 4K 3840x2160)​

**Cpu** → Full CPU description (brand, series, clock speed)​

**Ram** → RAM capacity in GB (converted to integer)​

**Memory** → Storage configuration string (combinations of HDD/SSD and capacities)​

**Gpu** → Full GPU description (e.g., Intel HD Graphics 620, NVIDIA, AMD Radeon)​

**OpSys** → Operating system (Windows, Mac, Chrome OS, Linux/Others)​

**Weight** → Laptop weight in kg (converted to float)​

**Price** → Target variable: selling price in INR (continuous numeric)​

### During preprocessing, additional engineered features are created such as:​

**PPI (Pixels Per Inch)** – derived from resolution and size, capturing display sharpness.​

**CPU Brand** – simplified CPU category (Intel Core i3/i5/i7, AMD, other Intel processors).​

**GPU Brand** – GPU vendor (Intel, Nvidia, AMD).​

**HDD / SSD** – separate numeric capacities extracted from the composite Memory column.​

**Touchscreen / IPS** – binary indicators parsed from ScreenResolution text.
___

## 🛠️ Skills & Tools Used

- **Programming & Data Handling**

  - **Python:** Pandas, NumPy for data cleaning, feature extraction, and transformation.​

  - **Data Visualization:** Matplotlib, Seaborn for distributions, brand analysis, heatmaps, and feature impact plots.​

- **Machine Learning Algorithms:** Linear Regression, Decision Tree, Random Forest, Support Vector Machine.​

- **Feature Engineering:**
  - Parsing resolution to compute PPI.
  - Splitting storage into HDD and SSD capacities.
  - Extracting CPU and GPU brands.
  - Creating binary flags for IPS and touchscreen features.
  - One Hot Encoding on categorical variables (company, type, OS, CPU-GPU brand, IPS, Touchscreen).
  - Standard Scaling on Numerical features (PPI, Ram, HDD, SSD, Weight).​
    
- **Model Evaluation & Validation:** R² Score, MAE, MSE, RMSE, MAPE, Median Absolute Error (MedAE).​

- **Correlation analysis** and **Heatmaps** for numerical features (Price, RAM, Weight, PPI, HDD, SSD, Touchscreen, IPS).
___
## 🔎 Key EDA Insights
- **Market segmentation by brand**
  - Premium brands like Apple, Razer, MSI, and LG show the highest mean and maximum prices, indicating a strong focus on performance and high-end configurations.​
  - Budget-oriented brands such as Mediacom, Vero, Chuwi, and Fujitsu offer significantly lower mean prices, targeting cost-conscious users.​
  - Mainstream brands like Dell, HP, Lenovo, and Asus span the full spectrum, providing budget, mid-range, and premium options with wide price variation.

- **Price distribution**
  - The price histogram is strongly right-skewed, with most laptops priced between ~10,000 and 100,000 INR and a long tail of expensive premium models above 100,000 INR.

- **Form factor and usage segment**
  - Notebooks dominate the market, followed by Gaming and Ultrabook categories, reflecting a mix of general-purpose and performance-focused machines.
  - Gaming and Workstation laptops typically command higher average prices due to powerful GPUs, higher RAM, and better displays.

- **Screen size and popularity**
  - 15.6‑inch laptops are the most common (~665 units), followed by 14.0, 13.3, and 17.3 inches, confirming 15.6 as the default mainstream form factor.​​

- **Storage & performance trends**
  - Strong positive correlation between SSD and both RAM and PPI: high-performance laptops tend to bundle SSDs, more RAM, and sharper displays.​
  - HDD is negatively correlated with SSD and RAM, highlighting a clear shift from HDD-based storage to SSDs in higher-end machines.

 - **Display & weight relationships**
   - Higher PPI and IPS/touchscreen features show mild positive correlation with weight, suggesting that feature-rich, sharper displays add slightly to the form factor.

**Overall, EDA shows that price is heavily driven by brand positioning, RAM, storage type, display quality, and form factor, with premium stacks of SSD + high PPI + more RAM forming the high-price cluster.**
___
## 🤖 Modeling Approach & Performance Summary
- The dataset is cleaned, transformed, and split into training and testing sets after feature engineering for RAM, storage, PPI, CPU/GPU brands, OS, and display features.​
- Multiple regression models are trained (including linear and tree-based ensemble methods), and evaluated 
- These results show that SVM achieved the best overall performance, with the highest R² and lowest RMSE, indicating it captures the underlying price patterns slightly better than Random Forest while maintaining similar error levels. Random Forest remains highly competitive and more interpretable, with very close MAE/MAPE, making it a strong alternative when model robustness and feature importance analysis are prioritized. The Decision Tree lags behind both ensemble and kernel-based approaches, highlighting the value of more complex methods for modeling non-linear relationships in laptop pricing.
___
## 🧠 Business Value

- Consumers can estimate fair laptop prices before purchase.
- Retailers can optimize pricing strategies and inventory planning.
- Manufacturers gain insights into which hardware upgrades justify higher prices.

By combining predictive accuracy with interpretability, this project delivers a transparent and trustworthy laptop pricing solution.
___
## 📌 Conclusion

- This project demonstrates how machine learning regression models, combined with thoughtful feature engineering and evaluation, can accurately predict laptop prices and uncover meaningful market insights.
- The approach balances performance, explainability, and real-world relevance, making it suitable for both academic learning and industry applications.
​
