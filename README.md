WRDS-Based Corporate Financial Analysis & Visualization

1. Problem & User
This project provides a reproducible Python workflow to analyze and visualize a firm’s historical financial performance and stock market valuation. It is designed for finance students, researchers, and analysts who need a structured pipeline to explore profitability trends, earnings metrics, and market multiples using WRDS data.

2. Data
- Source: Wharton Research Data Services (WRDS)
- Compustat Funda (annual financial statements)
- CRSP Monthly Stock File (year-end prices)
- Access: Data retrieved via Python `wrds` API in April 2025
- Key Fields:
- Financial: revenue, gross profit, net income, operating cash flow, capex, common equity, shares outstanding, share repurchases, EPS
- Market: year-end closing price (CRSP)

3. Methods (Main Python Steps)
1. Data Retrieval: 
   - `get_compustat_data()` pulls standardized annual financial statements from Compustat using SQL.
   - `get_crsp_price()` extracts December year-end prices from CRSP and aligns them by year.
2. Financial Indicator Calculation:
   - `compute_indicators()` derives gross margin, net margin, ROE, free cash flow, and buyback per share from raw financials.
   - `merge_price_pe()` combines stock prices with financial data to compute the P/E ratio.
3. Visualization:
   - `plot_profitability_trend()` plots gross margin, net margin, and ROE over time.
   - `plot_eps_bar()` visualizes annual EPS as a bar chart.
   - `plot_price_pe_trend()` shows stock price, EPS, and P/E ratio on a dual-axis chart.
   - `plot_normalized_comparison()` scales ROE, net margin, EPS, and P/E for side-by-side trend comparison.

4. Key Findings
- The pipeline enables clear identification of profitability drivers and margin trends over time.
- Year-end stock prices and derived P/E ratios reveal changes in market valuation relative to earnings performance.
- Normalized plots highlight alignment or divergence between fundamental metrics (e.g., ROE) and market multiples (e.g., P/E).
- The modular structure makes it easy to extend to peer comparisons or sector-level analysis.


5. Product link / Demo




6. Limitations & next steps
The current version only uses annual data; extending to quarterly or monthly data would allow more granular trend analysis.
The workflow is single-firm focused; future work could add peer benchmarking and sector averages.
The analysis does not currently adjust for inflation or accounting changes, which could affect multi-year comparability.
Next steps include adding dividend yield and total return metrics, and deploying an interactive dashboard with Streamlit.
