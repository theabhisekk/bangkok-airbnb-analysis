# Bangkok Airbnb Listings Analysis

Python analysis of 31,000+ real Airbnb listings in Bangkok to understand pricing, host behaviour, reviews and forward demand.

## Dataset
Inside Airbnb, Bangkok snapshot dated 29 June 2026 (listings, calendar, neighbourhoods). Source: insideairbnb.com/get-the-data. Prices are in Thai Baht (THB).

## Business Questions
1. How does room type affect price?
2. Which neighbourhoods are the most expensive?
3. Do hosts with more listings charge more?
4. What relates to review scores?
5. How booked-up are future months?

## Tools
Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

## Data Cleaning
- 14 of 90 columns were entirely empty and were removed
- Prices were text with symbols and commas; converted to numeric
- 2,082 listings (6.7%) had no price and were removed
- Removed the top and bottom 1% of prices (below ฿289, above ฿19,256) to limit outliers; used medians
- Calendar data (11.3M rows) was filtered to cleaned listings; it had no price column, so demand is measured by unavailable days

Final dataset: 28,410 listings across 50 neighbourhoods.

## Key Findings
- Entire homes have a median price of ฿1,712 vs ฿1,392 for private rooms (+23%)
- Parthum Wan is the priciest district (median ฿2,640, about 66% above the city median of ฿1,592)
- Median price barely differs by host size; hosts with 6+ listings control about 65% of listings
- Price, review count and availability show almost no correlation with review score (all |r| < 0.1)
- Forward unavailability rises from about 9% (Sep 2026) to about 32% (Apr-Jun 2027); this may include host-blocked dates

## Limitations
The calendar shows future availability, not past bookings, and unavailable days can mean booked or blocked by the host.

## How to Run
1. Download the Inside Airbnb Bangkok files into `data/raw/`
2. `pip install pandas numpy matplotlib seaborn`
3. Open `notebooks/analysis.ipynb` and run all cells