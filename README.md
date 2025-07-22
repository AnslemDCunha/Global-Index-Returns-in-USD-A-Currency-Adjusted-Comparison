# Global Stock Market Analysis: A USD-Adjusted Performance Comparison

### Project Overview

This project analyzes the performance of major stock market indices from the world's top economies. The core objective is to provide a fair comparison by converting all local currency returns into a common currency, the US Dollar (USD). This reveals the "true" return for a USD-based investor and highlights the significant impact of currency fluctuations on international investments.

The analysis identifies the top 15 global economies based on the latest World Bank GDP data and then visualizes their stock market performance from 2010 to the present day.

---

### Key Questions

1.  Which country's stock market has provided the highest returns over the last decade?
2.  How does stock market performance change when adjusted for currency exchange rates against the USD?
3.  Are high-growth economies translating that growth into stock market returns for international investors?

---

### Data Sources

* **Economic Data:** Gross Domestic Product (GDP) data for all countries was sourced from the [**World Bank Open Data API**](https://data.worldbank.org/indicator/NY.GDP.MKTP.CD).
* **Market Data:** Historical daily closing prices for stock indices and currency exchange rates were fetched from the [**Yahoo Finance API**](https://finance.yahoo.com/) using the `yfinance` library.

---

### Technology Stack

* **Language:** Python 3.x
* **Libraries:**
    * `pandas` for data manipulation and analysis.
    * `yfinance` for accessing financial market data.
    * `matplotlib` & `seaborn` for data visualization.
    * `Jupyter Notebook` for interactive development and analysis.

---

### Methodology

The analysis followed a structured workflow:

1.  **Identify Top Economies:** Fetched the most recent GDP data (for the year 2023) from the World Bank to programmatically identify the top 15 global economies.
2.  **Data Ingestion:** Pulled historical daily price data from January 1, 2010, to the present for the primary stock index and the corresponding local currency (vs. USD) for each of the top economies.
3.  **Currency Adjustment:** Converted the daily closing prices of each non-US stock index from its local currency into USD. This is calculated as:

    $$
    \text{Index Price in USD} = \text{Index Price in Local Currency} \times \text{Exchange Rate (Local to USD)}
    $$

4.  **Performance Normalization:** To compare growth trajectories, all USD-adjusted index values were normalized to a base value of 100, starting from the first trading day of 2010. This allows for an "apples-to-apples" comparison of percentage growth over time.
5.  **Visualization:** Plotted the normalized, USD-adjusted returns on a single line chart with a logarithmic scale to effectively compare markets with vastly different growth magnitudes.

---

### Visualizations

The primary output is a time-series plot comparing the normalized performance of each country's main stock index in USD terms.

*(To embed your chart, save the plot from your notebook as `returns_chart.png` in your project folder, then uncomment the line below by removing the `<!--` and `-->`)*

<!-- ![Global Stock Market Performance in USD](returns_chart.png) -->

---

### Key Findings & Insights

> The analysis reveals that the performance of emerging markets and the impact of a strong dollar are the dominant themes of the last decade.

* **Top Performers:** The stock markets of **India (Nifty 50)** and the **United States (S&P 500)** were the standout performers, delivering substantial returns even after adjusting for currency. India's growth trajectory, in particular, highlights the potential of emerging economies.
* **The Currency Effect:** Markets like **Japan (Nikkei 225)** have shown strong performance in their local currency (JPY) at various times. However, when converted to USD, these gains are significantly diminished, especially during periods of a strong dollar. This underscores the critical importance of currency risk for international investors.
* **European Lag:** Most major European indices, including **Germany (DAX)** and **France (CAC 40)**, showed more modest growth compared to the US and India, indicating a period of slower economic expansion translating into weaker market returns for USD-based investors.
* **Log Scale Is Key:** Using a logarithmic scale on the Y-axis was essential. It prevents the chart from being skewed by top performers (like India) and allows for a more meaningful comparison of the percentage growth rates across all countries, including the laggards.

---
