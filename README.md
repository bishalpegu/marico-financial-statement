# Marico Limited (NSE: MARICO) — Three-Statement Model & DCF Valuation

An integrated three-statement financial model and discounted cash flow valuation of **Marico Limited**, the Indian consumer-staples company behind Parachute, Saffola and a growing portfolio of premium personal-care and foods brands.

The model is built from audited consolidated filings. It runs a two-segment revenue forecast through a fully linked income statement, balance sheet and cash flow statement, then values the business on unlevered free cash flow under Bear, Base and Bull scenarios.

> **Base case: ₹320 per share vs. ₹775 market price (22-Oct-2026) — 59% implied downside.**
> The gap comes from the discount rate and long-run growth the market is pricing, not from the operating forecast (see [Key findings](#key-findings)).

---

## Valuation summary

| Scenario | Value per share (₹) | Upside / (downside) | Enterprise value (₹ cr) | Terminal growth |
| --- | ---: | ---: | ---: | ---: |
| Bear | 180 | (77%) | 23,792 | 5.0% |
| **Base** | **320** | **(59%)** | **41,947** | **6.0%** |
| Bull | 458 | (41%) | 59,884 | 6.5% |

| Base-case metric | Value |
| --- | ---: |
| WACC | 11.47% |
| Terminal value, % of EV | 80.7% |
| Implied EV / FY27E EBITDA | 15.2x |
| Market-implied EV / FY27E EBITDA | 36.7x |
| Implied P/E on FY27E EPS | 20.9x |
| Model integrity | All checks pass |

*₹ crore unless stated. Fiscal year ends 31 March. Valuation date 23-Oct-2026.*

---

## Repository contents

```
marico-equity-research/
├── marico-financial-statement.xlsx   # Three-statement model and DCF
└── README.md
```

## Workbook structure

| Sheet | Purpose |
| --- | --- |
| **Cover** | Valuation summary, workbook map, colour conventions, sources and modelling notes |
| **Assumptions** | Scenario selector (cell `C3`) and Bear / Base / Bull drivers for FY27E–FY31E, with historical ratios for reference |
| **Historicals** | Reported consolidated P&L, balance sheet, cash flow and segment data (FY22A–FY26A), each figure source-noted |
| **Model** | Segment revenue build, integrated income statement, condensed balance sheet, indirect cash flow and key ratios |
| **WACC** | CAPM cost of equity, after-tax cost of debt and market-value capital weights |
| **DCF** | Unlevered FCF, mid-year discounting with FY27 stub period, perpetual-growth terminal value, EV-to-equity bridge and two 5×5 sensitivity tables |
| **Checks** | 17 integrity checks, 2 warning flags and a master status cell |

```
Historicals ──► Model (actuals)
Assumptions ──► Model (forecasts) ──► DCF ◄── WACC
                     │                 │
                     └──────► Checks ◄─┘
```

## Methodology

**Revenue build**
- **India:** prior-year revenue × (1 + underlying volume growth) × (1 + price/mix)
- **International:** prior-year revenue × (1 + constant-currency growth) × (1 + FX translation impact)

**Operating model**
- Material cost, A&P, employee cost, other expenses, D&A and capex are forecast as a percentage of revenue
- Working capital is driven by receivable days (on revenue) and inventory and payable days (on material cost)
- Other income is earned on *opening* cash and treasury balances, and finance cost is charged on *opening* debt and leases, so the model has **no circular references**

**Valuation**
- Unlevered FCF = NOPAT + D&A − capex (incl. right-of-use additions) − increase in net working capital
- Mid-year discounting from the valuation date; FY27E includes only the stub period to 31-Mar-2027
- Gordon-growth terminal value on FY31E unlevered FCF
- Equity bridge adds cash and treasury investments and deducts borrowings, lease liabilities, the ₹2,055 cr obligation to buy non-controlling interests and book NCI (all at 31-Mar-2026)

**Cost of capital**

| Input | Value |
| --- | ---: |
| Risk-free rate (India 10Y G-sec) | 7.47% |
| Adjusted beta (Blume, raw 0.51) | 0.67 |
| Equity risk premium | 6.0% |
| Cost of equity | 11.50% |
| After-tax cost of debt | 5.99% |
| Equity / debt weight | 99.45% / 0.55% |
| **WACC** | **11.47%** |

## Key assumptions (Base case)

| Driver | FY26A | FY27E | FY31E |
| --- | ---: | ---: | ---: |
| India underlying volume growth | 8.0% | 8.0% | 6.0% |
| India price / mix | 18.1% | 3.0% | 3.5% |
| International constant-currency growth | 20.0% | 15.0% | 10.0% |
| Material cost, % of revenue | 55.5% | 53.5% | 52.0% |
| A&P, % of revenue | 9.6% | 10.3% | 10.3% |
| EBITDA margin | 17.1% | 18.1% | 19.6% |
| Effective tax rate | 20.4% | 23.0% | 23.0% |

The rationale for each driver is documented in the Assumptions sheet (rows 112–120).

## Key findings

- **Steady compounding:** base-case revenue grows at a 10.6% CAGR from ₹13,611 cr (FY26A) to ₹22,505 cr (FY31E), and EPS at a 12.5% CAGR from ₹13.59 to ₹24.50, as copra deflation lifts EBITDA margin by 2.5 percentage points.
- **High returns, net cash:** ROE rises from 43% to about 49%, and net cash (excluding the NCI obligation) grows from ₹2,019 cr to ₹3,108 cr despite an 80% payout.
- **What the price implies:** a reverse DCF on base-case cash flows shows that ₹775 requires a **WACC of about 8.3%** (at 6% terminal growth) or **terminal growth of about 9.4%** (at 11.47% WACC).
- **Sensitivity:** value ranges from ₹240 to ₹492 across WACC ±1 pp and terminal growth ±1 pp. A 1 pp change in WACC moves value by ₹50–70 per share, against about ₹20 per share for a 1 pp change in EBITDA margin.

## How to use

1. Open `marico-financial-statement.xlsx` in Microsoft Excel (sensitivity tables use array formulas).
2. Go to **Assumptions** and set cell `C3`: `1` = Bear, `2` = Base, `3` = Bull.
3. All statements, the DCF, sensitivities and the Cover summary update automatically.
4. Confirm that **Checks!M28** reads `ALL CHECKS PASS`.

**Colour conventions:** blue = hardcoded input / reported figure · black = formula · green = link to another sheet.

## Model integrity

The **Checks** sheet verifies, for every period:

- Balance sheet balances (historical and forecast)
- Cash flow closing cash ties to balance-sheet cash
- Cash-flow net income equals P&L net income, and owners' equity rolls forward correctly
- Historical PBT and EBITDA tie to reported figures; segment revenue sums to total revenue
- Sensitivity-table centre cells equal the headline value per share
- Terminal growth stays below both WACC and the risk-free rate

Warning flag: terminal value is 80.7% of EV, above the 75% review threshold.

## Data sources

| Period / item | Source |
| --- | --- |
| FY25A–FY26A financials | [Marico Integrated Annual Report FY2025-26](https://marico.com/investorspdf/Marico_Annual_Report_FY26.pdf) |
| FY23A–FY24A financials | [Audited consolidated results, Board Meeting Update, 6-May-2024](https://marico.com/investorspdf/Board_Meeting_Update_-_May_6,_2024.pdf) |
| FY22A revenue and EBITDA | Annual Report FY2025-26, five-year highlights |
| FY26 operating KPIs | [Q4 FY26 Results media release](https://marico.com/investorspdf/Media_Release_Q4FY26.pdf) |
| Share price, beta, 10Y G-sec | NSE close via Trendlyne, Business Today and Trading Economics (unofficial aggregators, to be verified) |

## Limitations

- FY22 shows revenue and EBITDA only; full audited statements were not available from an official source, and no figures were estimated.
- The forecast balance sheet is condensed: treasury investments, goodwill, leases, the NCI put obligation and other non-current items are held flat.
- No future acquisitions or NCI buy-out cash flows are modelled.
- Market inputs come from unofficial aggregators and should be verified against NSE, Bloomberg and RBI/CCIL data.
- Q2 FY27 results (board meeting 2-Nov-2026) are not yet reflected.

## Roadmap

- [ ] Verify market inputs and refresh WACC
- [ ] Add a peer comparables sheet (HUL, Dabur, Godrej Consumer, Emami, Colgate-Palmolive India)
- [ ] Add an exit-multiple terminal value cross-check
- [ ] Update for Q2 FY27 results

## Author

**Bishal** — MBA candidate, IIM Kozhikode (PGP 2024–26)

Part of an independent equity research portfolio covering Indian listed companies.

## Disclaimer

This model was prepared for independent academic and learning purposes only. It is not investment advice or a recommendation to buy, sell or hold any security. Figures are drawn from public filings and third-party market data that may contain errors, so verify them independently before relying on them.
