# Chinook EDA: Business Questions in SQL

Exploratory analysis of the **Chinook** sample database (a digital music store) using SQL on SQLite, run in DBeaver.

## Dataset

Chinook models a music store: customers buy tracks, and each purchase is recorded as an invoice.

| Table | What it contains |
|---|---|
| `Customer` | Customers, their country and assigned support rep |
| `Employee` | Store staff, including support reps |
| `Invoice` | One row per purchase (date, country, total) |
| `InvoiceLine` | One row per track in each invoice (price, quantity) |
| `Track` | Songs, with album, genre and media type |
| `Album` | Albums, linked to an artist |
| `Artist` | Artists |
| `Genre` | Music genres |
| `MediaType` | File formats |
| `Playlist` / `PlaylistTrack` | Playlists and the tracks they contain |

**Main relationships**

`Customer → Invoice → InvoiceLine → Track → Album → Artist`
`Track → Genre`
`Customer.SupportRepId → Employee`

## Business Questions

**Customers**
1. Who are the top 10 customers by spend, and what share of total revenue do they represent?
2. Which customers spent more than the average customer?
3. Which customers never made a purchase?

**Revenue**
4. What is the revenue by year and month?
5. What is the average invoice by country, and which countries are above the overall average?
6. What is the revenue by genre and its share of the total?

**Products**
7. Who are the top 5 artists by tracks sold?
8. Which albums have more than 10 tracks?
9. What is the best-selling genre in each country?

**Team**
10. How much revenue do the customers of each support rep generate?

## Key Findings

1. **Top customers:** [top 10 customers account for X% of revenue]
2. **Above-average customers:** [N customers out of M]
3. **Customers without purchases:** [0 customers: every customer has at least one invoice]
4. **Revenue over time:** [trend, best and worst months]
5. **Average invoice by country:** [countries above average]
6. **Genres:** [top genre and its share, e.g. X%]
7. **Top artists:** [top 5 names]
8. **Albums with 10+ tracks:** [N albums]
9. **Top genre by country:** [common pattern or exceptions]
10. **Support reps:** [rep with the highest revenue]

## SQL Techniques Used

`JOIN` (multiple tables), `LEFT JOIN`, `GROUP BY`, `HAVING`, subqueries, CTEs, window functions (`ROW_NUMBER`), `strftime` for dates.
