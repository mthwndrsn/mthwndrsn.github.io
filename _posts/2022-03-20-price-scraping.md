---
layout: post
title: How Automated Price Scraping Transformed an Australian eCommerce Retailer
categories: Automation, Case Study
---
Price is a key determinant of success. Customers can effortlessly compare prices across multiple platforms, and as an eCommerce business, keeping up with this constant price comparison is essential. For one prominent Australian eCommerce retailer, the solution to this challenge was price scraping technology. By automating competitor price monitoring, this retailer was able to dramatically improve operational efficiency and boost gross transaction value (GTV) and gross profit (GP). Let’s dive into how they achieved this through a case study of their implementation.

### The Problem: Manual Price Tracking Wasn't Scalable

Initially, this retailer’s pricing strategy relied heavily on manual processes. The buying and category management teams would monitor competitor websites, adjusting prices across 400 SKUs (stock keeping units) daily. A time-and-motion study revealed that these teams were spending around 60 hours each day on this task — equating to over $260,000 in annual salary costs.

With plans to grow from 80,000 SKUs in FY21 to 300,000 by FY25, scaling the manual price tracking system would have required significant additional headcount, adding unnecessary operational costs.

### The Solution: Implementing a Price Scraping Approach

To solve these challenges, the retailer invested in a price scraping system to automate the process. The goal was to implement software that could automatically scrape competitor prices and integrate these insights into the retailer’s pricing model, allowing them to react quickly and strategically.

This automation reduced the need for manual price monitoring and enabled the retailer to adjust prices in real time, thereby remaining competitive without increasing their staffing costs.

### The Technical Side: How Price Scraping Works

Price scraping works by using bots to scan competitor websites for price data, which is then collected, cleaned, and stored for analysis. Here's a simplified version of how a price scraping bot might be coded in Python using popular libraries like BeautifulSoup for web scraping and Pandas for data management:

```python
import requests
from bs4 import BeautifulSoup
import pandas as pd

# Define the URL of the competitor's product page
url = 'https://www.competitor.com/product-page'

# Send a request to the website
response = requests.get(url)

# Parse the HTML content of the page
soup = BeautifulSoup(response.text, 'html.parser')

# Scrape the price data (assuming the price is inside a <span> with a specific class)
price = soup.find('span', class_='product-price').text

# Store the data in a DataFrame for analysis
data = {'Product': ['Product A'], 'Competitor Price': [price]}
df = pd.DataFrame(data)

# Print the scraped data
print(df)
```

The retailer’s solution would have been much more sophisticated, incorporating multiple competitor websites and product pages, but the core principle remains the same. Data is collected, stored, and then analysed to generate actionable insights.

### Benefits of Automated Price Scraping

#### 1. **Improved Efficiency**

The most immediate benefit was a significant reduction in manual work. By automating the price tracking of competitors, the company saved 60 hours a day in labour, which translated into cost savings. Furthermore, these freed-up resources were redirected to more strategic activities, such as optimising the product selection and developing promotional campaigns.

#### 2. **Increased GTV and GP**

The automated tool enabled the retailer to better understand their competitors’ pricing in real time, allowing them to make dynamic pricing decisions. By adjusting prices to stay competitive, the retailer saw an improvement in both GTV and GP.

The case study reported a 0.05% improvement in GP margin, resulting in significant financial gains:

- **GTV (Gross Transaction Value)** increased from $620 million in FY21 to $1.35 billion in FY25, a growth of over 30% annually.
- **GP (Gross Profit)** improved in parallel, resulting in a positive net present value (NPV) of $466,000 over three years.

#### 3. **Real-Time Market Responsiveness**

Before automation, the manual process introduced significant delays in price adjustments, leading to lost sales opportunities. With automated price scraping, prices could be updated in real time. The retailer could either match or beat competitors’ prices almost instantly, reducing the risk of price mismatches that could drive customers away.

#### 4. **Reduced Need for Additional Headcount**

One of the primary justifications for this investment was the rapid growth in the number of SKUs. Without automation, the company would have needed to hire more staff to handle price monitoring. By automating this function, they avoided the need for additional headcount as their SKU count grew, saving potentially hundreds of thousands of dollars in salary costs annually.

### Unquantified Benefits: A Strategic Edge

In addition to the measurable financial gains, the automated price scraping system provided valuable unquantified benefits:

- **Promotional Optimisation**: The tool helped identify which products had the highest demand elasticity, meaning the retailer could plan promotions more strategically.
- **Better Product Introduction**: As the retailer introduced private label goods and new SKUs, they could track how these products performed in the market, enabling more informed sourcing and pricing decisions.
  
### Cost Breakdown and ROI

The retailer’s initial investment of $578,000 (including $445,000 in one-off costs and $133,000 in ongoing operating expenditure) returned a positive NPV of $466,000 over three years. The payback period was a quick 1.3 years, making it a highly worthwhile investment. Additionally, sensitivity analysis showed that even with a smaller than expected GP margin improvement (as low as 0.02%), the project would still have been profitable.

### Lessons for Other eCommerce Businesses

This Australian eCommerce retailer’s case highlights the power of automation for any business operating at scale. Manual processes can become bottlenecks, especially in fast-moving markets where pricing can change daily or even hourly. By automating these processes, businesses not only reduce costs but also position themselves to respond more swiftly to market changes.

If your business handles a large volume of products, price scraping can be an effective way to ensure you remain competitive, without manually checking your competitors’ prices. The savings in both time and labour can be substantial, and the ability to react in real time to pricing changes can help you avoid losing sales.

### Conclusion
For eCommerce businesses, price scraping isn’t just a competitive advantage — it’s becoming a necessity. By automating competitor price tracking, you can focus on growing your business and making strategic decisions without being bogged down by the manual grind of daily price monitoring. Just as this Australian retailer did, businesses that embrace price scraping can boost their profitability, streamline operations, and set themselves up for scalable success.