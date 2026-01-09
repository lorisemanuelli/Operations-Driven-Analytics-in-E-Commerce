# Slide 1 — Operations-Driven Analytics in E-Commerce
- Program: Capstone Projects 121 & 122 (2025–2026)
- Team 121 — “Operations-Driven Analytics in E-Commerce”
- Presenter: Loris Emanuelli
- First Approach Presentation
- Date: [Add session date]

Speaker Notes: Welcome the audience, set the scene with the flash sale vignette, and remind everyone this is the exploratory kickoff for our capstone direction.

---

# Slide 2 — Agenda
- Opening scenario and objectives
- Why operations-driven analytics matters
- Highlights from Mišić & Perakis review
- Newsvendor fundamentals and example
- Relevance, limits, and next steps
- Discussion and references

Speaker Notes: Walk through the flow, noting that the presentation culminates in immediate next actions and an invitation for feedback.

---

# Slide 3 — Supply Chain Insight: Responsive Inventory
- Analytics drives adaptive reorder policies
- Integrates sales, returns, and supplier signals
- Supports omnichannel stock allocation
- Enhances service levels while containing costs

Speaker Notes: Reference the review’s emphasis on data-enabled inventory management, and tie it to real-world e-commerce fulfillment variability.

---

# Slide 4 — Supply Chain Insight: Last-Mile Orchestration
- Routing data highlights emerging bottlenecks
- Delivery windows updated with real-time load
- Balances speed commitments with capacity
- Aligns customer promises with operational reality

Speaker Notes: Use Amazon-style slot management as an example of analytics feeding back into operations, underscoring relevance to our logistics scope.

---

# Slide 5 — Revenue Management Insight
- Demand models shape dynamic pricing
- Assortment decisions reflect stock positions
- Markdown tools target overstocks
- Segmentation tailors promotions without chaos

Speaker Notes: Emphasize how pricing levers interact with inventory levels, and how targeted actions derive from richer analytics.

---

# Slide 6 — Newsvendor Intuition
- Single-period inventory decision
- Balance between stockouts and leftovers
- Underage cost captures lost margin and loyalty
- Overage cost reflects holding or liquidation loss

Speaker Notes: Introduce the Newsvendor story, emphasizing the intuitive tug-of-war between ordering too little and too much.

---

# Slide 7 — Newsvendor Mechanics
- Demand modeled with distribution \(F(q)\)
- Critical fractile \( \frac{C_u}{C_u + C_o} \)
- Optimal order \( q^* = F^{-1}(\text{critical fractile}) \)
- Higher underage cost pushes target level up

Speaker Notes: Present the key formula clearly, pausing to interpret the fraction and what it means for service level decisions.

---

# Slide 8 — Flash Sale Example
- Sell price €120; purchase cost €70
- Liquidation value €40 → \(C_o = €30\)
- Lost margin \(C_u = €50\)
- Demand: Normal(900, 180) → \(q^* ≈ 958\)
- Result: 62.5% service level target

Speaker Notes: Walk through the calculation step by step to reinforce the applicability and show how inputs translate to actionable order quantities.

---

# Slide 9 — Mapping to E-Commerce Decisions
- Availability planning for limited windows
- Returns-adjusted demand estimates
- Perishables and fast-fashion stakes
- Promotion-driven procurement choices
- Omnichannel liquidation strategies

Speaker Notes: Connect each bullet to our team’s context—how the Newsvendor lens informs stocking, returns handling, and promotional readiness.

---

# Slide 10 — Out of Scope (Today)
- No feature-based demand modeling deep dive
- Machine learning forecasts reserved for later
- Preview: richer models will refine inputs
- Focus now on classical operations toolkit

Speaker Notes: Clearly draw the boundary so stakeholders know what to expect in future sessions and why today stays foundational.

---

# Slide 11 — Limitations & Risks
- Demand distributions may miss tail risk
- Cost parameters hard to estimate precisely
- Seasonality and shocks break calibration
- Single-period assumption simplifies reality

Speaker Notes: Acknowledge the caveats candidly, stressing the need for stress testing and organizational alignment when applying the model.

---

# Slide 12 — Potential Datasets
- JD.com flash sale transaction archives
- Amazon last-mile routing benchmarks
- Retail returns and refurbishment logs
- Promotional calendar and fulfillment data

Speaker Notes: Highlight how these datasets can anchor empirical work, and note any access considerations or proxies we might use.

---

# Slide 13 — Next Steps
- Deepen literature synthesis and case catalog
- Specify data needs and sourcing plan
- Build baseline Newsvendor prototype tool
- Coordinate stakeholder interviews

Speaker Notes: Outline immediate actions for the team, linking them back to building capability and gathering actionable insights.

---

# Slide 14 — Closing & Discussion
- Operations analytics bridges insight and action
- Newsvendor offers shared language for trade-offs
- Invitation: What scenarios should we model first?
- Thank you for feedback and collaboration

Speaker Notes: Summarize the core message and pose the discussion question to engage the audience right after the presentation.

---

# Slide 15 — References
- Velibor V. Mišić & Georgia Perakis, “Data Analytics in Operations Management: A Review”
- Wikipedia, “Newsvendor model”
- “Capstone Projects 121 & 122 2025–2026 Main Doc and Resources”

Speaker Notes: Mention that full citations will appear in our written materials and invite the audience to revisit the sources for deeper context.
