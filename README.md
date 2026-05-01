# Do-Data-Breaches-Actually-Hurt-Companies-Analyzing-the-stock-market
Marcell Brown 
Intro to data science - ECON 4970
Georgia state university 
April 2026


## Project Overview
The Story Behind This Project

Every few months, a headline breaks: another massive company has been hacked, millions of customer records exposed, and personal data stolen. We hear about the breach, we worry about our information, and then, life moves on. But what actually happens to these companies? Do they face real financial consequences, or do they simply issue an apology and continue business as usual?

This question motivated me to dig into the data. As someone interested in both finance and cybersecurity, I wanted to know whether the stock market which is essentially a reflection of how investors feel about a company's future  actually punishes corporations for failing to protect their customers' data. And if it does, does the size of the company matter? Can a trillion dollar company simply absorb the damage while smaller companies struggle to recover?

## Research Questions

1. Do publicly traded companies recover their stock price within one year of a data breach?
2. Does company size (market cap) affect how quickly a company recovers?
3. Is there a relationship between how many records were stolen and how badly the stock price dropped?

## Where I Found My Data/ Dataset

I used two datasets from Kaggle:

 **Data Breach Data**: [World's Biggest Data Breaches and Hacks]
(https://www.kaggle.com/datasets/joebeachcapital/worlds-biggest-data-breaches-and-hacks/data)
  This dataset documents major data breaches worldwide, including the organization affected, the date of the breach, the number of records lost, and the method of attack.

- **Stock Price Data**: [Massive Yahoo Finance Dataset]
(https://www.kaggle.com/datasets/iveeaten3223times/massive-yahoo-finance-dataset)
  This dataset contains daily stock prices for 491 of the world's largest publicly traded companies from 2018 to 2023, sourced from Yahoo Finance.
I used both websites to download my dataset and read them into R studio.
I matched companies that appeared in both datasets  meaning they were both publicly traded AND experienced a major data breach between 2018 and 2023.

This gave me 6 companies to analyze:

| Company | Ticker | Breach Date | Records Exposed |
|---------|--------|-------------|-----------------|
| Equifax | EFX | July 2019 | 147 million |
| Marriott | MAR | November 2018 | 500 million |
| Meta | META | April 2021 | 533 million |
| Uber | UBER | September 2022 | 57 million |
| Capital One | COF | July 2019 | 106 million |
| T-Mobile | TMUS | August 2021 | 54 million |

## What I Did

Using R, I calculated the average stock price for each company in the 30 days before and 30 days after their breach date. This allowed me to measure the immediate financial impact. I also tracked how long it took each company's stock to return to its pre-breach price, which I defined as "recovery."

I then built three visualizations to help answer my research questions.
## Figures and Analysis

### Figure 1: Does Breach Size Actually Matter?
<img src = "https://github.com/marcellb-067/-Do-Data-Breaches-Actually-Hurt-Companies-Analyzing-the-stock-market/blob/main/breach_size_vs_stock_drop.png">
This scatter plot compares the number of records exposed in each breach to the percentage change in stock price afterward. If breach size drove stock drops, we would expect to see a clear downward trend  bigger breaches causing bigger drops. Instead, the data shows almost no relationship. Marriott and Meta both lost over 500 million records, yet Marriott's stock fell 10.77% while Meta's rose 10.77%.

### Figure 2-6: Stock Price Before and After Each Breach
These line charts show each company's stock price from 180 days before to 365 days after their breach date. The red dashed line marks the exact breach date so you can see how the stock reacted in real time.

<img src = "https://github.com/marcellb-067/-Do-Data-Breaches-Actually-Hurt-Companies-Analyzing-the-stock-market/blob/main/EFX_breach_impact.png">
(Equifax's stock actually rose slightly after the 2019 breach announcement, likely because the market had already priced in the risk from the original 2017 breach.)

<img src = "https://github.com/marcellb-067/-Do-Data-Breaches-Actually-Hurt-Companies-Analyzing-the-stock-market/blob/main/COF_breach_impact.png">
(Capital One fell 5.39% after their 2019 breach, recovering within 2 days. The relatively quick recovery may reflect investor confidence in the company's response and remediation efforts.)

<img src = "https://github.com/marcellb-067/-Do-Data-Breaches-Actually-Hurt-Companies-Analyzing-the-stock-market/blob/main/MAR_breach_impact.png"> 
(Marriott saw the sharpest immediate drop of any company in the dataset, falling nearly 11% in the 30 days after their 2018 breach was announced.)

<img src = "https://github.com/marcellb-067/-Do-Data-Breaches-Actually-Hurt-Companies-Analyzing-the-stock-market/blob/main/META_breach_impact.png">
(Even though META exposed 533 million users' data, the largest breach in the dataset Meta's stock rose over 10% in the following month, suggesting the market had little concern about the long-term impact.)

<img src = "https://github.com/marcellb-067/-Do-Data-Breaches-Actually-Hurt-Companies-Analyzing-the-stock-market/blob/main/TMUS_breach_impact.png"> 
(T-Mobile had the longest recovery of any company in the dataset at 353 days (nearly a full year). This may reflect the fact that T-Mobile had experienced multiple breaches in prior years, diminishing investor confidence.

<img src = "https://github.com/marcellb-067/-Do-Data-Breaches-Actually-Hurt-Companies-Analyzing-the-stock-market/blob/main/UBER_breach_impact.png">
(Uber dropped 6.29% immediately after their 2022 breach but recovered within a single trading day, showing great resilience.)

### Figure 7: How long does it take to recover?
<img src = "https://github.com/marcellb-067/-Do-Data-Breaches-Actually-Hurt-Companies-Analyzing-the-stock-market/blob/main/recovery_by_market_cap.png">
This bar chart tells us that while most companies recovered within days, T-Mobile stood out dramatically taking 353 days to return to its pre-breach stock price. Marriott came in second at 81 days. The remaining four companies recovered in 2 days or less, which raises an important question: are markets simply not punishing companies for data breaches?

## What I learned/The big takaway
The biggest takeaway from this analysis is that for large, publicly traded companies, data breaches barely seem to matter to the stock market. Four out of the six companies I analyzed recovered their pre breach stock price within two days. Two days. Uber dropped 6% and bounced back the next trading day. Capital One fell 5% and recovered in 48 hours. Meta exposed over 500 million users' personal data and their stock actually went up the following month. It's hard not to look at these numbers and feel like corporations are simply not being held accountable for failing to protect people's data.The two outliers in the data  Marriott and T-Mobile  were interesting for different reasons. Marriott took 81 days to recover, which was the second longest in the dataset. Their breach was one of the largest in history at 500 million records, and the fact that it involved a hotel chain where customers store passport numbers and travel information may have made investors more nervous than usual. T-Mobile was the most striking case, taking 353 days to recover. After doing more research I found that T-Mobile had experienced several other breaches in the years leading up to the 2021 incident, which likely explains why investors were less forgiving. When a company keeps getting hacked, eventually the market loses patience.Overall this project taught me that the stock market is not always the best judge of corporate accountability. Large companies have the resources, brand recognition, and investor loyalty to weather a data breach without serious financial consequences. 

## Files in This Repository
- `breach_stock_analysis.R` — All R code used for this analysis
- `breaches.csv` — Data breach dataset from Kaggle
- `stock_details_5_years.csv` — Stock price dataset from Kaggle
- `EFX_breach_impact.png` — Equifax stock chart
- `MAR_breach_impact.png` — Marriott stock chart
- `META_breach_impact.png` — Meta stock chart
- `UBER_breach_impact.png` — Uber stock chart
- `COF_breach_impact.png` — Capital One stock chart
- `TMUS_breach_impact.png` — T-Mobile stock chart
- `recovery_by_market_cap.png` — Recovery time bar chart
- `breach_size_vs_stock_drop.png` — Breach size scatter plot

## Tools Used
- **R** with packages: `dplyr`, `ggplot2`, `scales`
