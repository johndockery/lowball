# lowball

A Claude Code skill that generates realistic lowball offers for home listings.

Paste a Zillow/Redfin URL and it'll open the listing in Chrome, find every flaw, estimate repair costs, and draft a polite-but-devastating offer message 15-35% below asking.

## Usage

```
/lowball https://www.zillow.com/homedetails/...
```

## Requirements

- [Claude Code](https://claude.com/claude-code)
- Chrome DevTools MCP server (for reading listings)

## Install

Clone this repo and open it in Claude Code:

```bash
git clone https://github.com/johndockery/lowball.git
cd lowball
claude
```

Then use `/lowball` with any listing URL.

## Example

> `/lowball https://www.zillow.com/homedetails/156-west-lake-rd-wilmington-vt/...`

```
Subject: Offer on 156 West Lake Road, Wilmington, VT — $975,000

Dear Ms. Wimmelman,

My clients have toured 156 West Lake Road and are genuinely drawn to the
property — the Lake Raponda setting is special, and the single-owner history
speaks to how well it's been loved. That said, after careful review, we'd like
to present the following concerns that inform our offer.

Condition & Systems:
- The home was built in 1989 — making it 37 years old. With no mention of
  updates to the roof, HVAC, septic, or well system in the listing, we have to
  budget conservatively for deferred maintenance. A roof replacement on a home
  this size in southern Vermont runs $18,000–$25,000. Septic inspection and
  potential replacement: $15,000–$40,000. HVAC modernization: $12,000–$18,000.
- The primary heat sources appear to be a wood-burning fireplace and wood
  stove — charming, but not a modern heating system. Adding or upgrading forced
  air or radiant heat is a significant capital expense ($20,000–$35,000).
- At 2,944 sq ft with 3 bedrooms and 4 bathrooms, the layout raises
  questions — the bath-to-bedroom ratio is unusual and may reflect a floorplan
  that doesn't maximize usable living space.
- The lot is only 0.8 acres, which is modest for a $1.3M lakefront property in
  rural Vermont.

Market Position:
- The town's assessed value is $840,970 — a 54% gap between assessment and
  asking price.
- A comparable Lake Raponda listing at 197 Lake Raponda Rd (4 bed, 3 bath,
  1.72 acres) is listed at $1,697,000, but that property offers a larger lot,
  more bedrooms, and over twice the acreage.
- The listing has been on market only 7 days, but the sparse detail on systems
  and mechanicals suggests a property that will face scrutiny from informed
  buyers.

Estimated remediation costs: $65,000–$118,000

Given the age of the home, the likely capital needs, and the assessed value, we
are offering $975,000 — which we believe reflects fair market value adjusted for
condition. This accounts for the waterfront premium while being realistic about
what a 1989 home with original systems will require.

We are serious buyers, pre-approved, and flexible on timeline. We'd welcome a
conversation to find terms that work for everyone.

Respectfully,
[Your Name]
```
