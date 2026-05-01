# -Do-Data-Breaches-Actually-Hurt-Companies-Analyzing-the-stock-market
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

Using R, I calculated the average stock price for each company 
in the 30 days before and 30 days after their breach date. This 
allowed me to measure the immediate financial impact. I also 
tracked how long it took each company's stock to return to its 
pre-breach price, which I defined as "recovery."

I then built three visualizations to help answer my research 
questions.


