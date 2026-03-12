# /lowball

Generate a realistic lowball offer for a home listing by mining public records for every flaw and using them as leverage. Paste a Zillow/Redfin URL or describe a property to get started.

## What it does

1. Searches the web for listing data across multiple aggregator sites
2. Identifies the city/county and discovers the relevant open data portals
3. Queries public records APIs for building permits, code violations, housing violations, 311 complaints, tax assessments, and environmental data
4. Cross-references listing claims against public records (sqft discrepancies, unit count mismatches, valuation gaps)
5. Writes a polite but devastating offer letter backed by hard data

## Example output

The following offer was generated for [285A Kingsland Ave, Brooklyn NY 11222](https://www.zillow.com/homedetails/285A-Kingsland-Ave-Brooklyn-NY-11222/30621425_zpid/) — a $3.2M FSBO listing in Greenpoint.

---

**Subject: Offer on 285A Kingsland Ave, Brooklyn NY 11222 — $2,150,000**

We're genuinely drawn to 285A Kingsland — the renovation has real character, and the location near McGolrick Park is excellent. That said, our due diligence has surfaced a number of concerns that make us unable to meet the asking price.

**Property concerns:**

- The building is 125 years old (built 1901) on a narrow 18.92' x 100' lot with no garage or outdoor parking. The "rose pink" roof, while distinctive, will need full replacement within 5-10 years ($25-40K for a Brooklyn walk-up).
- Square footage is reported as 2,610 (Zillow), 2,376 (Redfin), and 3,735 (NYC tax records) — three different numbers from three sources. We'd need to verify actual livable area.
- Tax records show 5 units; the listing describes a duplex plus a loft rental. If units were combined without C of O amendments, that's a compliance issue.

**Public records findings:**

- NYC DOB records show Job #320912492, an Alteration Type 1 permit filed November 2018 that has been renewed **6 times** through February 2025 — over 6 years of continuous construction permits. A plumbing permit was issued as recently as October 2024.
- DOB issued **10 Class 1 "Immediately Hazardous" violations** in May 2019. Four of these were paid off on March 2, 2025 — days before the listing appeared. The timing raises questions about what was being resolved.
- HPD records show **open violations** for failure to file a valid registration statement (2015, 2016, 2023, and 2024 — a recurring pattern). There is also an open bed bug reporting violation from April 2024.
- 311 records include a **hazardous materials / chemical odor complaint** (August 2025) and an **excessive water in basement** complaint (August 2025) — the DEP determined the water issue was an interior condition.
- The property sits on the western boundary of the **Meeker Avenue Plume**, an EPA Superfund site added to the National Priorities List in March 2022, contaminated with tetrachloroethylene and trichloroethylene (known carcinogens). The listing's mention of an "EPA tested and approved mitigation system in the basement" confirms proximity to this contamination.
- NYC's own assessed market value is **$563,000**. Zillow's Zestimate is ~$1,226,000. Redfin estimates $1,428,879-$1,850,128. The Greenpoint median is $1,675,000. Every automated valuation is well below $3.2M.
- The property last sold in **August 2021 for $1,500,000** — the current ask represents a 113% markup in under 5 years.

**Our offer: $2,150,000**, reflecting the open violations, environmental risk, unresolved permits, and the significant gap between every third-party valuation and the asking price. We believe this is fair given the full picture. Happy to discuss — we'd love to make this work.

---

## Research summary

The offer above was built from these public data sources, all queried live via NYC Open Data APIs:

| Source | API | Key findings |
|--------|-----|-------------|
| DOB Permits | `data.cityofnewyork.us/resource/ipu4-2q9a.json` | 8 permits on one job spanning 2018-2025, still active |
| DOB Violations | `data.cityofnewyork.us/resource/3h2n-5cm9.json` | 10+ Class 1 hazardous violations, 4 paid days before listing |
| HPD Violations | `data.cityofnewyork.us/resource/wvxf-dwi5.json` | Open registration failures (recurring since 2015), open bed bug violation |
| 311 Complaints | `data.cityofnewyork.us/resource/erm2-nwe9.json` | Chemical odor, basement flooding, repeated illegal parking |
| DOB Complaints | `data.cityofnewyork.us/resource/eabe-havv.json` | 18 complaints spanning 2005-2023 |
| Tax Assessment | `data.cityofnewyork.us/resource/8y4t-faws.json` | Market value $563K, zoning R6B, tax class 2A, 5 units |
| EPA/Superfund | Web search | Meeker Avenue Plume Superfund site borders Kingsland Ave |
| Sales History | Web search | Last sold Aug 2021 for $1.5M |
| Valuations | Web search | Zestimate ~$1.2M, Redfin estimate $1.4-1.85M |
