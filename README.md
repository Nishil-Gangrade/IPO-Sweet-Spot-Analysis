# IPO Sweet Spot Analysis 📊

## 📌 Project Overview
This project analyzes 2 years(01 January 2024 - 25 September 2025) of IPO data (578 companies across 12 sectors) to identify the **sweet spot strategy** for investors:  
➡️ Which IPOs to apply for to maximize **listing-day profit** while maintaining a reasonable **chance of allotment**.  

We built a complete analytics pipeline in **Python (Pandas, NumPy, Matplotlib, Seaborn, Plotly)** and visual dashboards (Excel & Power BI) to study the relationships between **sector, subscription levels, and market size**.

---

## ⚡ Key Insights
- **Sector Analysis**: Finance, IT & Telecom, and FMCG delivered the highest median listing gains.  
- **Subscriptions**: Strong positive correlation (r ≈ 0.62) between total subscriptions and listing gains.  
  - Low subs (0–25%) → ~0% gain  
  - Mid-High subs (50–75%) → ~28–33% gain ✅ *best balance*  
  - High subs (75–100%) → ~90% gain but very low allotment chance  
- **Market Cap**: Mid-Large IPOs (upper-mid market cap) gave the highest consistent gains (~25–46%).  
- **Sweet Spot Strategy**:  
  - Sector = top 3 profitable (by median gain)  
  - Subscription = mid-high quartile (50–75%)  
  - Market Cap = mid-large quartile  
  - ✅ These IPOs yielded strong returns with a realistic allotment chance.  
- **Sector × Subscription Ranking**: At equal subscription levels (e.g., 100x), Finance & IT dominated returns.  

---

## 📂 Project Structure
📁 IPO-Sweet-Spot-Analysis
│── ipo_data.xlsx # Raw dataset (578 IPOs, 2022–24)
│── ipo_analysis.ipynb # Jupyter Notebook (full analysis workflow)
│── ipo_clean.xlsx # Cleaned dataset (after preprocessing)
│── sector_summary.xlsx # Sector-level profitability summary
│── total_sub_bins_vs_gain.xlsx # Subscription vs profit quartile table
│── marketcap_bins_vs_gain.xlsx # Market cap quartile analysis
│── top3_sectors_per_subsrange.xlsx
│── results/ # Exported plots (PNG/HTML)
│ ├── sector_mean_gain.png
│ ├── sector_median_gain.png
│ ├── total_sub_vs_gain.png
│ ├── marketcap_vs_gain.png
│ ├── sweet_vs_others_scatter.png
│ ├── top_vs_sweet_vs_others.png
│ ├── sweet_vs_all_line.png
│ ├── sector_vs_subsrange_heatmap.png
│ └── top_vs_sweet_vs_others_totalsub.html (interactive)
│── README.md # Project documentation


---

## 🛠️ Tools & Libraries
- **Python**: Pandas, NumPy, Matplotlib, Seaborn, Plotly  
- **Excel**: Used for dataset storage & summary exports  
- **Power BI**: for dashboarding & interactive sector analysis  

---

## 📊 Visual Highlights

### Sector Profitability
![Sector Profitability](results/sector_median_gain.png)

### Subscription vs Gain
- Mid-high subs (50–75%) give ~30% returns with better allotment chance.  
![Total Subscriptions vs Gain](results/total_sub_vs_gain.png)

### Market Cap Effect
- Mid-Large caps outperform.  
![Market Cap vs Gain](results/marketcap_vs_gain.png)

### Sweet Spot IPOs vs Others
- Pink = sweet companies, Gold = top 5 all-time gainers, Blue = rest.  
![Sweet vs Others](results/top_vs_sweet_vs_others.png)

### Sector vs Subscription Range (Heatmap)
- Ranking of sectors at equal subscription demand (e.g., 100x+ subs).  
![Sector vs Subscription Heatmap](results/sector_vs_subsrange_heatmap.png)

---

## 📑 How We Did It  

1. **Data Collection**  
   - IPO dataset was created by **web scraping** [Trendlyne IPO Features](https://trendlyne.com/features/) since no ready Excel/CSV data was available.  
   - Collected details for **578 IPOs (2022–2024)** including:  
     - Company name, sector, listing date  
     - Issue price, issue size, market cap  
     - QIB / HNI / Retail / Total subscriptions  
     - Listing open & close price, listing gain %, current gain %  
   - Exported scraped results into `ipo_data.xlsx`.  

2. **Data Cleaning**  
   - Removed symbols (`Rs`, `%`, `Cr`, `x`), fixed missing values, and converted dates.  
   - Standardized numeric columns (prices, subscriptions, gains).  
   - Encoded sectors numerically for easier analysis.  
   - Final cleaned dataset stored as `ipo_clean.xlsx`.  

3. **Exploratory Analysis**  
   - **Sector-wise median gains** to identify consistently profitable industries.  
   - **Correlation & scatter plots** to study how subscriptions affect listing gains.  
   - **Market cap quartiles** (Small → Large) to analyze size effect on IPO performance.  

4. **Sweet Spot Strategy**  
   - Defined investor-friendly filter:  
     - Subscription = **Mid-High quartile (50–75%)**  
     - Sector = **Top 3 profitable sectors**  
     - Market Cap = **Mid-Large quartile**  
   - Extracted shortlisted IPOs (`ipo_candidates.xlsx`).  
   - Validated with scatter plots showing **Sweet Spot vs Others vs Top 5 gainers**.  

5. **Sector × Subscription Ranking**  
   - Ranked sectors within each subscription band (0–25x, 25–50x, 50–100x, 100x+).  
   - Revealed which sectors outperform **at equal demand levels**.  
   - Example: Finance & IT dominated in high subscription bands, while Healthcare/FMCG showed resilience at lower levels.  




---

## 🎯 Final Recommendation
> Investors aiming for **listing-day profit** should target IPOs with:  
> - **Mid-High subscriptions (50–75%)**  
> - **Mid-Large market cap**  
> - **Top 3 performing sectors (Finance, IT & Telecom, FMCG)**  
>  
> ✅ These IPOs gave ~28–33% average gains with higher allotment probability compared to the most oversubscribed issues.  

---

## 🚀 How to Run
1. Clone repo:  
   ```bash
   git clone https://github.com/your-username/IPO-Sweet-Spot-Analysis.git
   cd IPO-Sweet-Spot-Analysis


Install requirements:

pip install pandas numpy matplotlib seaborn plotly openpyxl


Open Jupyter Notebook:

jupyter notebook ipo_analysis.ipynb


Explore the interactive charts in results/ (HTML).

👨‍💻 Author

Nishil Gangrade — B.Tech CSE | Data Analytics & Web Development Enthusiast

Inspired by real-world IPO investing challenges & data-driven decision-making.

⭐ Acknowledgements

Dataset curated from public IPO listings (2022–2024).

Thanks to the open-source community for amazing Python tools.


---

