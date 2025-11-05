# Data Visualization Project

## Data

The data I propose to visualize is a Global AI Adoption & Impact table that I already integrated into my project.
Each row represents a Country × Year × Industry observation with the following fields:
•	Country, Year, Industry

•	AI Adoption Rate (%)

•	AI-Generated Content Volume (TBs per year)

•	Job Loss Due to AI (%)

•	Revenue Increase Due to AI (%)

•	Human–AI Collaboration Rate (%)

•	Top AI Tools Used (e.g., ChatGPT, Claude, Midjourney)

•	Regulation Status (Lenient / Moderate / Strict)

•	Consumer Trust in AI (%)

•	Market Share of AI Companies (%)
This dataset lets me compare adoption, output, economic effects, workforce effects, and policy/trust context across places, industries, and time.





## Questions & Tasks

These questions drive the design and interactions:
1.	How does AI adoption change over time by industry and country?
Task: Track AI Adoption Rate (%) across years; compare slopes across industries.
2.	Is there a relationship between adoption and output?
Task: Check correlation between AI Adoption Rate (%) (X) and AI-Generated Content Volume (Y), by industry and year.
3.	What are the trade-offs between revenue gains and job displacement?
Task: Plot Revenue Increase (%) vs Job Loss (%) with size = Market Share; highlight industries in each quadrant.
4.	Do regulation and trust move together?
Task: Compare Consumer Trust (%) across Regulation Status levels; facet by region or industry.
5.	Which tools dominate where?
Task: Summarize Top AI Tools Used by industry/country and relate to Market Share.
6.	Where is collaboration actually happening?
Task: Explore Human–AI Collaboration Rate (%) vs Adoption to spot sectors using AI as augmentation vs automation.


## Sketches

<img width="518" height="290" alt="image" src="https://github.com/user-attachments/assets/cea1f4a5-df3b-4e0e-864d-312b9f568562" />




## Prototypes

I’ve created a proof-of-concept interactive scatter plot:

•	What it shows: Any two chosen metrics (e.g., AI Adoption Rate (%) vs AI-Generated Content Volume).
Color = Industry; optional size = Market Share (sqrt scale).

•	Interactions:
o	Year & Industry filters
o	X/Y metric dropdowns
o	Percent axis toggles with proper tick formatting
o	Tooltips (Country · Industry · Year + exact values)
o	Optional mean aggregation when “All years” is selected (reduces clutter)

•	Why it works: A scatter is the fastest way to see relationships and outliers across multiple sectors and years. The controls turn one view into a compact exploration tool that answers several questions without leaving the page.


<img width="1310" height="607" alt="image" src="https://github.com/user-attachments/assets/3f7bb0bc-9bdf-47cf-9d46-2910a88b52a1" />

```
[![image](https://user-images.githubusercontent.com/68416/65240758-9ef6c980-daff-11e9-9ffa-e35fc62683d2.png)](https://vizhub.com/curran/eab039ad1765433cb51aad167d9deae4)
```

For my Project Progress Assisgment for October 01, I was able to make updates to my model, which included the following: 

•	Legend placement & layout: Moved the categorical legend into a right-side gutter and added a soft background so it no longer overlaps the Y-axis. Increased right margin to make room.

•	Size legend: Added a compact bubble legend (3 reference sizes via quantiles) that updates with filters and shows the current size metric’s label/units.

•	Y scale toggle (Linear/Log): New control to switch Y between linear and log. Safely falls back to linear if values are non-positive.

•	Quadrant overlay: Draws median crosshairs, shows counts per quadrant, and includes a short guidance note explaining the axes and medians.

•	Improved tooltips: Consistent number/percent formatting, shows N when rows are aggregated (All years), and includes the size metric name/value when used.

•	Defaults & robustness: Smarter column detection (adoption, displacement, volume, market share), percent-aware tick labels, sqrt size scaling, and aggregation to Country×Industry means when “All years” is selected.

<img width="1477" height="602" alt="image" src="https://github.com/user-attachments/assets/2407f8d2-2245-4c12-af90-5acf09e0b923" />

October 07, 2025 Updates
What’s new
•	Trust × Regulation small multiples: you can flip into a 3-up view (Lenient / Moderate / Strict). All three facets share the same X/Y scales and encodings, so differences pop without mental rescaling.

•	“All years” aggregation selector: choose mean / median / latest when viewing multiple years. This lets us compare stable centers (median), average behavior (mean), or the most recent snapshot (latest) without changing filters.

•	A11y + keyboard flow: every control now has an associated <label for> + id, ARIA labels, and a clean tab order. You can fully operate the viz via keyboard.

What stayed from Week 2
•	Right-side industry legend (no longer collides with axes) + size legend (three reference bubbles).

•	Y linear/log toggle, quadrant medians overlay (single-view), and improved tooltips (consistent number/percent formatting, N shown when aggregated, size metric included).

•	Robust column detection, percent-aware ticks, sqrt bubble sizing.

Why this matters
•	Faceting makes policy context (regulation status) immediately comparable—same frame, different slices.

•	Aggregation choice makes “All years” honest: you can decide which summary best fits the question.

•	Accessibility upgrades make it usable for more folks and easier to demo live.

<img width="1909" height="649" alt="image" src="https://github.com/user-attachments/assets/d9e4d66e-4432-4434-916a-ec1eca5f427b" />


What’s new October 21, 2025

Trends view (slope/line chart): Y = AI Adoption Rate (%), X = Year; one line per Industry within the selected Country.

Legend interactions: Click a legend item to isolate/hide a line (great for decluttering).

Temporal tooltip: Shows value and Δ vs previous year on hover.

Unified view switcher: A top control lets you jump between Scatter and Trends in the same app.

Quality-of-life: Clearer titles/labels that reflect filters; right-side legend panel spacing refined.

What stayed from last week

Explorable Scatter core: User-selectable X/Y metrics, Year & Industry filters, percent tick toggles.

Quadrant overlay: Median crosshairs with counts per quadrant for quick “gain vs pain” reading.

Size legend: Quantile-sized bubbles (when a size metric is active) remain for scale context.

Faceting by Regulation: Optional 3-up small multiples (Lenient / Moderate / Strict) with shared scales.

All-years aggregation options: Mean / Median / Latest still available for rollups.

Accessibility pass: Labeled controls, keyboard focus order, ARIA attributes.

Net effect: last week’s scatter stays your comparative “first look,” while the new Trends view adds direction and momentum over time, making it easier to explain how and how fast industries are moving—not just where they are right now.

<img width="1240" height="651" alt="image" src="https://github.com/user-attachments/assets/0ca460b5-5240-4040-b98e-1cd1f3b01c93" />

<img width="1079" height="662" alt="image" src="https://github.com/user-attachments/assets/6c9fe9e6-b9d6-4e74-a536-f6185597312d" />


What’s new — October 28, 2025 (Week 5: Filtering Power & Highlights)
•	Multi-select Industries + Spotlighting: Pick multiple industries at once; selected series/points pop with colored halos and thicker strokes while everything else fades to ~8% opacity. If nothing’s selected, the view returns to normal automatically.

•	Top-K filter: Show only the top K by Size (Market/Volume) or by Impact (X×Y) to focus on the most consequential items fast.

•	Shareable state: The app now writes your settings to the URL hash (view, metrics, filters), so you can copy the link and others see the exact same view.

•	Legend refinement in Trends: Click to toggle visibility; Alt/⌘-click to solo a single line for quick comparisons.

•	Polish: Clearer empty-state messages, steadier tooltip formatting, and consistent right-side legend spacing across views.

What stayed from last week
•	Explorable Scatter core: User-selectable X/Y metrics, Year filter, percent tick toggles, and median quadrant overlay for quick “gain vs pain” reads.

•	Size legend: Quantile bubbles still provide context whenever a size metric is active.

•	Faceting by Regulation: Optional 3-up small multiples (Lenient / Moderate / Strict) with shared scales remain available.

•	All-years rollups: Mean / Median / Latest aggregation options still supported.

•	Trends view: Slope/line chart of AI Adoption (%) vs Year, one line per series, with temporal tooltip (value + Δ vs previous year) and a unified view switcher to flip between Scatter and Trends.

Net effect: Last week gave us direction over time; this week adds control. You can now zero in on the exact industries that matter, pare the view down to the top movers, and share the precise state with one link, without losing the exploratory feel that made the scatter useful.

<img width="1723" height="743" alt="image" src="https://github.com/user-attachments/assets/5f797ca6-25ad-491c-abcc-7eb0fb643682" />

<img width="1107" height="708" alt="image" src="https://github.com/user-attachments/assets/b53a691c-7455-4978-89e7-9cfb4b9942da" />


What’s new — November 5, 2025 (Week 11 polish on previous week’s features)
•	Kept the multi-select highlighting workflow: the Industry multi-select still drives a “spotlight” mode — selected industries get color, stroke, and halo; everything else drops to low opacity so patterns are easier to read in dense views.

•	Top-K stays first-class: you can still switch between “None,” “Size,” and “Impact (X×Y)” and choose K (5/10/15/20) to strip the view down to the most consequential points.

•	URL hash persistence is active: view (Scatter/Trends), chosen metrics, year, selected industries, and Top-K mode are saved in the URL, so you can paste the link and classmates see the same slice.

•	Consistent legend panel: right-side legend remains, aligned with the updated font/styling, so both Scatter and Trends look like one app.

•	Light UI polish: wrapped controls, friendlier container styling, and clearer titles/axis labels to make the visualization more “shareable” for the final phase.

What stayed from last week
•	Explorable Scatter core (X/Y pickers, year filter, percent ticks).

•	Quadrant overlay (median crosshairs to read “gain vs pain” fast).

•	Highlight halos for selected industries.

•	Trends view with per-series tooltip (value + Δ vs previous year) and legend click to isolate.

•	All-years aggregation logic and the overall two-view structure.

Net effect: we didn’t change the mental model — we tightened it. You still explore first (scatter), explain second (trends), but now the view is cleaner, shareable, and looks closer to something you could show outside class.

<img width="1071" height="817" alt="image" src="https://github.com/user-attachments/assets/4fc2a166-9997-4255-94b8-ca834bf4a660" />

<img width="1062" height="790" alt="image" src="https://github.com/user-attachments/assets/f07697aa-bdab-4f87-8302-9c21dfbe79f4" />




## Open Questions

•	Percent vs. absolute scales. Some columns are percentages (0–100), others are counts/volumes. I’m confident about formatting, but I’m still deciding when to force 0–100 domains vs. auto-fit to data (especially after filtering/aggregation).
Mitigation: add a per-axis toggle (already partially implemented) and show min/max in the UI so users understand the current scale.

•	Aggregation when “All years” is selected. Right now I average X, Y (and size if present) across years per Country×Industry. Is mean the right summary (vs. median or last year)?
Mitigation: add a summary selector (mean/median/latest) and show the N of observations in the tooltip.

•	Outlier handling & readability. Content Volume can be skewed; a few points can dominate size/position.
Mitigation: add log scale toggle (especially for Y), and a size legend with cap + “≥” bucket.

•	Category explosion in color legend. Some filters may leave >10 industries, and the legend truncates.
Mitigation: add searchable multi-select for Industry plus a “highlight selected” mode; allow “Top K by size” filter.

•	Tooltip overlap and dense clusters. Overplotting can make identical/similar points hard to hover.
Mitigation: small jitter, optional Voronoi/quad-tree hover, and a focus state (dim others on hover/selection).

•	Data hygiene. Mixed CSV/TSV, stray percent signs, and possible 0–1 vs. 0–100 inputs.
Mitigation: keep robust coercion; add a tiny data validation panel (rows parsed, dropped, columns detected).

•	Comparability across geographies. Some variables might not be directly comparable across countries due to methodology.
Mitigation: document assumptions in README; allow per-country normalization (e.g., z-scores) as an advanced toggle.

•	Performance at scale. If the dataset grows (thousands of rows), DOM circles and tooltips may get sluggish.
Mitigation: switch to canvas rendering for marks while keeping SVG axes/labels if needed.

•	Accessibility & export. Need keyboard navigation and image export for reports.
Mitigation: add ARIA labels, focus order, and a “Download PNG” button.


## Milestones

Week 1 — Stabilize the core scatter (done / polish)

•	Finalize parsing (CSV/TSV auto-detect, percent coercion).

•	Confirm default encodings: X = AI Adoption Rate (%), Y = AI-Generated Content Volume, Color = Industry, Size = Market Share.

•	Add data validation panel (rows loaded, columns detected, dropped rows count).

•	README: dataset description + provenance.

Week 2 — Usability & clarity

•	Add size legend (3–4 bubbles with labeled values).

•	Add log/linear toggle per axis (start with Y).

•	Add quadrant overlay (median/mean crosshairs) with counts per quadrant and short guidance text.

•	Improve tooltips (aligned formatting, N when aggregated, size metric label).

Week 3 — Faceting and time

•	Build Trust × Regulation small multiples (3 columns: Lenient/Moderate/Strict; same X/Y per facet).

•	Add “All years aggregation method” selector (mean/median/latest).

•	Keyboard focus order + ARIA labels for controls.

Week 4 — Trends view

•	Implement slope graph / line chart: Y = Adoption (%), X = Year; one line per Industry within selected Country (or vice-versa).

•	Add legend click to isolate/hide lines; tooltip with delta vs. previous year.

Week 5 — Filtering power & highlights

•	Replace Industry single-select with multi-select + search; add highlight mode (non-selected dim to 20–30% opacity).

•	Add Top K filter by size or by X×Y “impact” score.

•	Persist UI state in URL hash so views are shareable.

Week 6 — Performance & refinement

•	Add optional canvas renderer for points when row count > threshold; keep SVG axes/legend.

•	Add Voronoi/quad-tree hover to reduce tooltip flicker in dense areas.

•	Mobile layout pass (controls wrap, legend collapses).

Week 7 — Storytelling & export

•	Add an annotation layer (callouts for notable outliers or policy changes).

•	Download PNG / Copy to clipboard export.

•	“About this data” panel with caveats and definitions.

Week 8 — Polish, tests, submission

•	Cross-browser check, light unit tests for parsing/formatting utilities.

•	Final README with screenshots, interaction guide, and example analysis answers to the project questions.
•	Record a short demo gif/video.

