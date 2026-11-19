Do Comparable Borrowers Pay the Same for a Mortgage?

A fair-lending review of 2.3 million US East Coast mortgage loans, 2023–2025

My team and I completed this project for MMA 860: Data Acquisition, Management and Visualization, taught by Prof. Keith Rogers, as part of the Master of Management Analytics program at Queen's University. The project included a proposal, a client report and a presentation.

Team: Nida Li · Terry Chen · Andy Chang · Jessica Ilok · Mohammad Mohtasim Hassan · Carina Avakian

The question

We framed the project for a lender's compliance team: do borrowers with similar finances pay different mortgage prices by race and ethnicity, and where should the review start?

What we did
Used public HMDA loan data covering 14 Atlantic states plus DC (the data itself isn't included here)
Used SQL (DuckDB) to cut a 6.2-million-row, 2.4 GB file down to comparable loans: 30-year fixed-rate home purchases
Cleaned the data in Python, with the rule "remove the impossible, keep the unusual," leaving 2.3 million loans
Measured price with the rate spread (APR above the market rate on the day the rate was set) and built a regression in steps, adding income, loan size, down payment, debt, loan type, state and year
Checked the results with F-tests, Bonferroni-adjusted t-tests, lender-clustered standard errors and Chow tests
What we found

Initial findings: before any controls, Hispanic borrowers paid about 20 bps more than non-Hispanic White borrowers, and Black borrowers about 6 bps more. A raw gap can't answer the question on its own, though, because the groups differ in income, down payment and loan type.

After comparing like with like:

Hispanic borrowers pay about 12.8 bps more, or about $32 a month ($380 a year) on an average $374,000 loan. The gap held steady from 2023 to 2025, and about 58% of it comes from using higher-cost lenders.
Asian borrowers pay about 10.7 bps less.
For Black borrowers, the gap disappears once their finances and loan features are taken into account.
Our recommendation

Make the Hispanic pricing gap the review's first priority. It passed every test we set and was positive in every state. Start in Maryland (+27.6 bps), then Connecticut, Virginia, New Jersey and New York, and look closely at how lender choice drives the gap.

One important limitation: the public data has no credit scores, so this is an unexplained gap worth reviewing, not proof of discrimination.

Reflection

Working on this with my team was a great experience. Handling a file this large, making careful cleaning decisions and making sure every one of us could explain the models was challenging at times, but it was all worth it. I learned a lot about turning messy real-world data into a clear answer for a client, and I'm proud of what we built together.
