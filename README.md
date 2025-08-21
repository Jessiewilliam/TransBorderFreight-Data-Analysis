# 🚛 TransBorder Freight Data Analysis (2020–2024)

This project analyzes U.S. North American TransBorder Freight data from 2020 to 2024 to uncover trends, inefficiencies, and patterns in freight movement across different transportation modes. The dataset is provided by the Bureau of Transportation Statistics (BTS)
## 📂 Project Structure
### Project Link:(https://drive.google.com/drive/folders/1xpvt-Ak-n1g7XgJYBUCzdzMCLoAxsp9u?usp=drive_link)
Each month folder contains multiple `.csv` files (e.g., `dot1_0720.csv`, `dot2_0720.csv`, etc.).

📁 data/

├── 2020/
│ ├── January2020TransBorderRawData/
│ ├── February2020TransBorderRawData/
│ └── ...

├── 2021/
│ ├── January2021TransBorderRawData/
│ ├── Febraury2021TransBorderRawData/
│ └── ...

├── 2022/
│ ├── January2022TransBorderRawData/
│ ├── February2022TransBorderRawData/
│ └──

├── 2023/
│ ├── January2023TransBorderRawData/
│ ├── February2023TransBorderRawData/
│ └──

├── 2024/
│ ├── January2024TransBorderRawData/
│ ├── Febraury2024TransBorderRawData/
│ └──
├── ...


## 🧠 Analysis Goals

Using the **CRISP-DM** methodology, we aimed to:

- 📌 **Understand patterns** in freight trade by transport type (rail, road, air, etc.)
- 📉 **Identify inefficiencies** by month and year
- 🛑 Highlight **safety or missing data concerns**
- 🌱 Estimate **environmental impacts** based on mode type and weight
- 📊 Visualize trade value trends across months and years

---

## ⚙️ Technologies Used

- `Python 3.11`
- `Pandas`
- `Matplotlib & Seaborn`
- `Jupyter Notebook`
- `Google Colab` (for cloud-based computation)

---

## 📈 Exploratory Data Analysis (EDA)

### ✅ Key Insights:
0
1. **Freight Value Fluctuations**:
   - Trade value was highest in **January 2020** and **January 2023**.
   - Sharp drops were observed during early pandemic months.

2. **Missing Year Data**:
   - Data for some years particularly **2021 and 2022** was partially missing or not available.

3. **Most Common Transport Mode**:
   - `DISAGMOT = 5` (likely Road) was the most frequent.

4. **Data Quality Issues**:
   - Some columns like `VALUE`, `SHIPWT`, and `FREIGHT_CHARGES` had `NaN` values.
   - Used `.fillna()` with mean/mode to clean.

5. **Monthly Trends**:
   - Performed grouped analysis for each year and generated bar charts for monthly trade values.

---

## 🧼 Data Cleaning Approach

```python
# Handling missing numeric data
df.fillna(df.mean(numeric_only=True), inplace=True)

# Handling categorical data
for col in df.select_dtypes(include='object').columns:
    if df[col].isnull().any():
        df[col] = df[col].fillna(df[col].mode()[0])

📊 Sample Visualization
python
Copy
Edit
# Bar chart of monthly total freight VALUE for 2021
monthly_value = df[df['YEAR'] == 2021].groupby('MONTH')['VALUE'].sum()
monthly_value.plot(kind='bar', figsize=(10,6), color='pink', title='Total Trade Value by Month in 2

📁 Files Included
Main_Transborder_Freight.ipynb – Full notebook with data loading, EDA, and visualizations

Copy_of_Main_Transborder_Freight.ipynb – Cleaned data sample

codes-north-american-transborder-freight-raw-data.pdf – Metadata and codebook


###🙋‍♂️ Author
Jessica William

📜 License
This project is for educational and analytical purposes only.


