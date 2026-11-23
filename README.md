# DailyDose / Ledger

Minimal, clinical-style, spreadsheet-like medication inventory and spending tracker. Single HTML file, no dependencies or server required.

## Use
Open `index.html` directly in a modern browser, or deploy it to GitHub Pages. Works on mobile and desktop. All data remains in that browser's local storage. Export JSON backups regularly; use Import to restore.

## Preloaded medications

| Medication | Daily dose | Tablet | Stock (initial assumption) | Pack | Price | Days per pack | 30-day use cost |
|---|---:|---:|---:|---:|---:|---:|---:|
| Lamotrigine | 200 mg | 200 mg | 30 | 30 | 2200 ₽ | 30 | 2200 ₽ |
| Aripiprazole | 10 mg | 10 mg | 30 | 30 | 2500 ₽ | 30 | 2500 ₽ |
| Quetiapine | 75 mg | 25 mg | 60 | 60 | 400 ₽ | 20 | 600 ₽ |

Total 30-day equivalent consumption cost: **5300 ₽**.

**Important:** Stock defaults to one full pack for demonstration because actual tablets on hand were not supplied. Edit each stock value to get a useful refill forecast.

## Calculation definitions
- Tablets per day = daily dose (mg) / tablet strength (mg).
- Days per pack = pack tablet count / tablets per day.
- Cost per 30 days = daily tablets × price per tablet × 30.
- Refill needed date = first day the current stock will not cover the dose. The app considers today's recorded dose when forecasting.
- Projected purchases in the next 30 days = cost of packs forecast to be needed during the next 30 calendar days, accounting for current stock and recorded doses. The 90-day purchase table shows forecasted purchases separately from the 30-day equivalent use cost.
- Marking a daily dose taken decreases stock by the number of tablets. Undo restores it. + Pack adds one pack to stock.

The app assumes a constant dose every day, unchanged prices, and that you obtain packs on the day needed. It is not a reminder system, prescription manager, dosing recommendation, or guarantee of pharmacy availability. Date projections may shift with missed doses or changes in dose. The data is stored per browser/device, not synchronized.