# Operations-Driven Analytics in E-Commerce — First Approach

**Presenter:** Loris Emanuelli  
**Estimated Duration:** ~20 minutes

---

## [00:00–01:00] Opening

Good afternoon everyone, and thank you for joining me. Picture the moment right before a flash sale on a fast-moving e-commerce platform: tens of thousands of shoppers refreshing their screens, fulfillment centers gearing up, and decision-makers wondering whether they will sell out too soon or end the day with warehouses full of unsold inventory. Today, I’m here to walk you through how we can tackle those questions with an operations-driven analytics lens. This is our first exploratory pass at the “Operations-Driven Analytics in E-Commerce” capstone, so think of it as setting the stage—identifying the concepts, tools, and opportunities that will guide our deeper work over the coming months.

---

## [01:00–03:00] Big Picture — Why Operations-Driven Analytics Matters

When we say “operations-driven analytics,” we’re talking about harnessing data not just to describe what happened, but to directly inform decisions on inventory, fulfillment, pricing, and service levels. In e-commerce, prediction and optimization live side by side. On one hand, we care about forecasting demand, understanding customer behavior, and measuring process performance. On the other hand, we want to translate those insights into concrete actions: how much to order, when to replenish, which fulfillment path to use, and what price to set in response to market signals.

The core promise is to move from intuition-led operations to analytically reasoned choices. That matters because e-commerce operates at thin margins, high velocity, and with customers who quickly migrate when service falters. Analytics-driven operations help us squeeze more value from every SKU and every time slot, all while keeping the customer experience intact. That’s the mind-set I want to center today: analytics as the connective tissue between what we believe the market will do and the operational levers we can pull.

---

## [03:00–08:00] Key Insights from “Data Analytics in Operations Management: A Review”

The survey by Velibor Mišić and Georgia Perakis gives us a disciplined view of how analytics is reshaping three pillars of operations: supply chain management, revenue management, and service operations. I’ll highlight the supply chain and revenue management pieces that are most relevant to our e-commerce focus.

First, on the supply chain side, the review emphasizes that data-driven inventory management is moving past static reorder points toward responsive policies that ingest real-time sales, returns, and supplier signals. One example the authors discuss is omnichannel fulfillment, where retailers integrate data from stores, distribution centers, and online channels to allocate stock dynamically. In practice, that means an order placed online might be shipped from a nearby store if analytics predicts stock imbalances elsewhere. The payoff is better service levels and lower carrying costs. For our project, this suggests that we can explore scenarios where inventory placement decisions are steered by predicted demand variability across regions or channels.

A second supply chain insight is the growing use of analytics to orchestrate last-mile logistics. The review references how e-commerce players mine routing data to anticipate bottlenecks, evaluate delivery promises, and balance speed with cost. Think about Amazon’s constant recalibration of delivery windows: the system monitors daily pick volumes and transportation capacity, then updates available slots to maintain reliability. These practices show the benefit of folding operational data back into planning loops, a theme we can leverage when we consider datasets like Amazon’s last-mile routing benchmarks.

Switching to revenue management, the paper highlights how dynamic pricing and assortment decisions are grounded in demand models that incorporate price sensitivity, inventory levels, and competitor behavior. Airlines pioneered these methods, but e-commerce retailers now use similar tactics to decide whether to discount overstocked items or hold prices firm when inventory is tight. For instance, a retailer might deploy a markdown optimization tool that looks at current stock, shelf life, and the estimated customer response to price changes. If the model predicts slow movement, prices are nudged down; if inventory is scant, prices stay high or even increase. This is a clear example of analytics bridging prediction—estimating demand at different price points—and optimization—choosing the price that maximizes margin subject to inventory constraints.

The review also reminds us that data analytics enables segmentation beyond crude averages. Retailers better understand which products or regions respond to promotions, allowing them to tailor strategies without exploding operational complexity. That kind of targeted action is essential when we start designing experiments or pilots for our capstone, because we will need to justify why certain SKUs or customer cohorts receive special analytical attention.

Finally, the authors acknowledge the organizational dimension: analytics initiatives require cross-functional alignment between data science teams and operations managers. In e-commerce, where the cadence is daily or even hourly, that alignment determines whether analytics outputs are actually used. For our capstone, we should think early about the operating rhythms of our hypothetical client and ensure that any analytics-driven recommendation fits into existing decision windows.

---

## [08:00–13:00] The Newsvendor Model — An Intuitive Walkthrough

Let me now pivot to the Newsvendor model, a cornerstone of inventory theory that will serve as a conceptual anchor for our study. Imagine a seller facing a single selling period—say a limited-time drop or a seasonal item. The seller must choose an order quantity before demand materializes. Order too little, and you miss sales, losing margin and possibly customer goodwill. Order too much, and you’re stuck with leftovers that tie up capital or require discounting.

Formally, the Newsvendor problem describes this single-period inventory trade-off. We define two cost parameters:

- `Cu`, the underage cost: the opportunity cost per unit of demand that could not be satisfied. This typically includes lost margin and sometimes the long-term cost of disappointing a customer.
- `Co`, the overage cost: the cost per unit of inventory left unsold at the end of the period. This could be the purchase cost minus any salvage value.

Demand is modeled as a random variable with cumulative distribution function \( F(q) \). The Newsvendor’s optimal order quantity \( q^* \) balances the expected marginal benefit of ordering one more unit against the marginal cost of leftover inventory. The classical result tells us:

\[
q^* = F^{-1}\left(\frac{C_u}{C_u + C_o}\right)
\]

The ratio \( \frac{C_u}{C_u + C_o} \) is often called the critical fractile. It tells us the service level at which we are indifferent between ordering another unit or stopping. If understocking is very expensive compared to overstocking, the critical fractile is high, nudging us to stock more.

Let me ground this with a quick example that resembles a flash sale for a limited-edition gadget. Suppose we sell a product for €120 and pay €70 per unit from the supplier. If we sell out, the margin per unit is €50. If stock remains after the event, we can liquidate leftovers for €40, turning the overage cost into \( C_o = 70 - 40 = €30 \). The underage cost is essentially the lost margin: \( C_u = €50 \).

Now, assume demand during the event follows a normal distribution with a mean of 900 units and a standard deviation of 180 units. The critical fractile becomes:

\[
\frac{C_u}{C_u + C_o} = \frac{50}{50 + 30} = \frac{50}{80} = 0.625
\]

We now ask: at what order quantity \( q \) does the cumulative distribution reach 0.625? For a normal distribution with mean 900 and standard deviation 180, the z-score associated with 0.625 is approximately 0.32. Translating back, \( q^* = 900 + 0.32 \times 180 \approx 957.6 \), so we would round to 958 units. This decision balances the risk of lost sales against the cost of holding or liquidating excess stock. If we believe that running out damages loyalty more than having leftover inventory, we can revise \( C_u \) upward and watch the critical fractile rise.

Managerially, the Newsvendor model offers intuition on how uncertainty and cost asymmetries shape ordering decisions. It highlights the value of demand forecasts, but also warns us that even perfect predictions of the mean are insufficient—we need to appreciate distributional uncertainty. Moreover, it gives us a language to discuss trade-offs with stakeholders: “Given our cost of overstocks versus understocks, we are targeting a 62.5% service level.” That is far more actionable than just saying “we hope to sell about 900 units.”

---

## [13:00–16:00] Relevance to Team 121’s E-Commerce Focus

How does this model and the broader operational analytics lens connect to our capstone theme? First, consider product availability. Many e-commerce categories—electronics, fashion, home goods—encounter seasonal demand spikes tied to promotions and holidays. The Newsvendor framework helps us reason about buy quantities when the selling window is limited. If we know the implied costs of under-ordering versus over-ordering, we can justify whether to lean aggressive or conservative in procurement.

Second, returns management complicates the picture. In categories with high return rates, the effective demand for inventory is lower, but returns also arrive as salvageable stock. Extending the Newsvendor logic, we can update demand distributions to reflect expected net sales after returns, or treat returns as a separate stochastic process feeding back into inventory. In practical terms, our team can explore datasets or case studies where return behavior is significant, such as apparel or consumer electronics.

Third, for perishable or time-sensitive items—think specialty foods or fast-fashion drops—overage costs can spike because unsold stock quickly loses value. The Newsvendor intuition then pushes us toward lower target service levels unless we can mitigate risk with cross-channel liquidation. Our capstone can investigate how omnichannel networks and marketplaces absorb leftover stock, reducing \( C_o \) and enabling more ambitious buy targets.

Finally, promotional planning provides a fertile ground. When running a limited-time promotion, marketing wants sufficient stock to avoid disappointing customers, while finance worries about margin erosion from leftovers. The Newsvendor framework offers a structured conversation. By plugging in promotion-specific demand forecasts and cost parameters, we can align decisions with analytical justification. This also opens the door to testing different promotional strategies in a sandboxed environment.

To make this concrete, we will look at potential datasets such as JD.com transaction logs that capture flash sales dynamics or Amazon’s last-mile routing data that influences actual fulfillment capacity. By tying these data sources to inventory decision points, we reinforce the operations-driven narrative: analytics informs not just what we promise customers but how we deliver.

---

## [16:00–17:00] Out of Scope Today

Before we move further, let me flag what is intentionally out of scope for this first presentation. We are not delving into feature-based demand models, machine learning forecasting pipelines, or granular customer segmentation techniques today. Those topics are important and absolutely on our roadmap, but they require a different depth of discussion around data engineering, model validation, and experimentation. What I can offer is a preview: as we build the foundational understanding of classical models like Newsvendor, we will later explore how modern machine learning tools can enrich the inputs—think better demand distributions, real-time elasticity estimates, and automated parameter updates. For now, we are focusing on the baseline operational analytics toolkit that will anchor those future enhancements.

---

## [17:00–18:30] Limitations and Risks

No model is a silver bullet, and the Newsvendor approach is no exception. Demand uncertainty can be heavier-tailed or multi-modal, meaning that simple distributions misrepresent tail risks. Cost estimation is another pain point: quantifying underage cost often involves intangible elements like customer goodwill or the reputational hit of stockouts, which are hard to pin down. Data seasonality and structural breaks can wreak havoc on forecasts; the demand distribution we calibrated last quarter may not hold during a sudden trend shift or supply disruption. Finally, the model’s reliance on a single-period assumption may oversimplify realities where inventory can roll over or be replenished mid-horizon.

Operationally, implementing Newsvendor-style decisions requires disciplined alignment between analytics and procurement. If teams do not trust the inputs, they revert to gut feel. That is why our capstone must anticipate change-management considerations and ensure that any analytic recommendation comes with transparency and stress testing.

---

## [18:30–19:30] Next Steps

From here, I propose three immediate next steps. First, deepen our literature review with targeted readings, including revisiting the Mišić and Perakis review to extract detailed cases and any data references we might replicate. Second, scope the data requirements for applying the Newsvendor logic in an e-commerce scenario: what demand history, cost parameters, and lead-time information do we need, and where can we source them? Third, build a baseline analytical prototype—perhaps a simple notebook that allows stakeholders to input demand assumptions and cost parameters and instantly see the recommended order quantity. This prototype can double as a communication tool when we talk to domain experts or sponsors.

---

## [19:30–20:00] Closing

Let me close by bringing it back to that flash sale scenario. Operations-driven analytics gives us the confidence to decide how much to stock, how to fulfill, and how to price, even when the clock is ticking and uncertainty looms. Classical models like Newsvendor equip us with intuition; modern data helps us refine that intuition. This first approach lays the groundwork for Team 121 to bring analytical rigor to e-commerce operations. Thank you for your attention, and I welcome your feedback as we continue shaping this capstone journey.

---

## Elevator Recap

In twenty minutes, we connected the promise of operations-driven analytics in e-commerce to practical insights from the operations management literature, unpacked the Newsvendor model with a realistic example, and mapped its relevance to our capstone focus on availability, returns, perishables, and promotions—setting a clear path for deeper analytics and data work in the next phase.

---

## Appendix: Newsvendor Math Notes (Not for Live Delivery)

- Let demand \( D \) have cumulative distribution \( F \). Decision variable: order quantity \( q \).
- Expected profit is \( p \mathbb{E}[\min(D, q)] - c q + v \mathbb{E}[(q - D)^+] \), where \( p \) is selling price, \( c \) is purchase cost, \( v \) is salvage value.
- Marginal condition: order one more unit if \( \mathbb{P}(D \ge q) \ge \frac{C_o}{C_u + C_o} \).
- Critical fractile \( \beta^* = \frac{C_u}{C_u + C_o} \) yields \( q^* = F^{-1}(\beta^*) \).
- Extensions include service level constraints, price-dependent demand, and multi-product variants with capacity coupling.

---

## References

- Velibor V. Mišić & Georgia Perakis, “Data Analytics in Operations Management: A Review,” Manufacturing & Service Operations Management.
- Wikipedia, “Newsvendor model.”
- “Capstone Projects 121 and 122 2025–2026 Main Doc and Resources.”
