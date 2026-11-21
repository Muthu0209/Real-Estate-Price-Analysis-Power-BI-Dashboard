# Real Estate Price Analysis – Power BI Dashboard

An end-to-end Power BI project that analyses residential property sales to help a real estate company decide **which segments to target and where to buy next**. The report was built in Power BI Desktop, published to Power BI Service, packaged as an App, and extended with Quick Insights, Q&A and a pinned dashboard with a mobile layout.

🔗 **Live Power BI App:** [Open in Power BI Service](https://app.powerbi.com/Redirect?action=OpenApp&appId=d34b69b4-43ce-488f-ad29-cd74f67597f0&ctid=c3d4f9b6-bc6f-447f-8af6-ec4ade2c86dc&experience=power-bi)
*(Requires a Power BI sign-in with access to the app. If you can't open it, please use the screenshots below.)*

---

## Business Problem

The company is a leading residential real estate firm planning to expand by purchasing new properties. Senior management needs data-backed answers to:

- How have sales volume and revenue changed over time?
- Which cities command the highest prices?
- How do property quality and condition affect price?
- Which cities have the most furnished properties?
- Do bedroom and bathroom counts drive price?

## Dataset

| Item | Detail |
|---|---|
| File | `data/Dataset.xlsx` (Sheet1 – sales data, Sheet2 – zip code reference) |
| Records | 21,313 rows / 21,137 unique properties (`cid`) |
| Coverage | 25 cities, sales in 2014–2015 |
| Key fields | `cid`, `Sold (year/month)`, `City`, `zipcode`, `price`, `quality`, `condition`, `furnished`, `room_bed`, `room_bath`, `living_measure`, `lot_measure`, `total_area`, `basement`, `yr_built`, `yr_renovated` |

## Tools & Skills

Power BI Desktop · Power BI Service · DAX · Power Query · Excel · Key Influencers (AI visual) · Q&A · Quick Insights

## Data Preparation

- `cid` converted to **Text**; `price` converted to **Fixed decimal number**
- Data types checked for consistency before modelling

**DAX measure**

```DAX
Percentage Properties Furnished =
DIVIDE(SUM('Sheet1'[furnished]), COUNTA('Sheet1'[cid])) * 100
```

## Dashboard Overview

**KPI cards:** Total properties (21.14K) · Average price ($540.23K) · Average total area (17.18K sq ft) · Average quality · % of properties furnished

**Visuals**

| Visual | Purpose |
|---|---|
| Sum of price & Count of properties by Sold year/month (combo chart) | Revenue and volume trend over time |
| Average price by City (map) | Geographic price distribution |
| Average price by Quality and Condition (stacked column) | Price premium for higher quality/condition |
| Count of properties by Bedrooms and Furnished (column) | Furnished vs unfurnished mix by bedroom count |
| Key Influencers (price) | What drives price up – bedrooms and bathrooms |

## Screenshots

### 1. Power BI Desktop – Main Report
`images/01-powerbi-desktop-report.jpg`


The full report page: KPI cards, revenue and volume trend by month, price map by city, price by quality and condition, bedroom/furnished distribution, and the Key Influencers visual. Shows that properties with more than 4 bedrooms are the strongest driver of higher price.

### 2. Dashboard Q&A – Top Cities by % Furnished
`images/02-dashboard-qna-top-cities-furnished.jpg`

Natural-language query *"top cities by percentage properties furnished"* in Power BI Service. Mercer Island leads (about 61% furnished), followed by Issaquah, Redmond, Bellevue and Woodinville.

### 3. Quick Insights
`images/03-quick-insights.jpg`

Auto-generated insights from the semantic model: Seattle has noticeably higher quality counts, an outlier in furnished % for zip code 98039, and a strong correlation between condition and living area.

### 4. Dashboard – Mobile Layout
`images/04-dashboard-mobile-layout.jpg`

Phone-optimised version of the dashboard with KPI tiles, average price by quality/condition and % furnished by city, so managers can check key numbers on the go.

## Power BI Service Dashboard

🔗 **[Open the Power BI Service Dashboard](https://app.powerbi.com/Redirect?action=OpenApp&appId=d34b69b4-43ce-488f-ad29-cd74f67597f0&ctid=c3d4f9b6-bc6f-447f-8af6-ec4ade2c86dc&experience=power-bi)**

Direct link: https://app.powerbi.com/Redirect?action=OpenApp&appId=d34b69b4-43ce-488f-ad29-cd74f67597f0&ctid=c3d4f9b6-bc6f-447f-8af6-ec4ade2c86dc&experience=power-bi

## Key Findings

- **Mercer Island** has the highest average price (about $1.20M) and the highest share of furnished homes (about 61%), pointing to a premium segment.
- **Quality** is the clearest price lever: average price rises sharply from quality grade 1 to 5.
- **Bedrooms** are the top price influencer; homes with more than 4 bedrooms are more likely to see a price increase.
- **Seattle** has by far the largest volume of properties (about 7,000 records, roughly a third of the data).

## Power BI Service Workflow

1. Published report from Desktop to a dedicated workspace
2. Reviewed the workspace lineage view
3. Created an **App** and managed access
4. Configured data source credentials and scheduled daily refresh
5. Generated **Quick Insights** from the semantic model
6. Built a **Dashboard** by pinning visuals, applied a theme, and created a mobile layout

## Repository Structure

```
├── README.md
├── Real_Estate_Price_Analysis.pbix
├── data/
│   └── Dataset.xlsx
└── images/
    ├── 01-powerbi-desktop-report.jpg
    ├── 02-dashboard-qna-top-cities-furnished.jpg
    ├── 03-quick-insights.jpg
    └── 04-dashboard-mobile-layout.jpg
```

## How to Use

1. Download `Real_Estate_Price_Analysis.pbix`
2. Open it in Power BI Desktop
3. If prompted, update the data source path to `data/Dataset.xlsx`

## Author

**Muthulakshmi Viswanathan** – Data Analyst, Toronto, Canada
[LinkedIn](https://www.linkedin.com/in/) · [GitHub](https://github.com/)
