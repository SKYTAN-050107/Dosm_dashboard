MALAYSIA SUSTAINABLE TOURISM ANALYTICS DASHBOARD
DOSM DATATHON 2026

DEPLOYED DASHBOARD
==================

Dashboard URL:
https://dosm-dashboard.vercel.app

The deployed version provides the full interactive dashboard.

5.1 SOFTWARE NAME AND VERSION USED
==================================

The dashboard is a web application developed using:

- Node.js 22.12 or newer
- React 18.3.1
- React DOM 18.3.1
- Vite 8.3.0
- @vitejs/plugin-react 6.1.1
- Express.js 5.2.1
- Recharts 3.10.1
- react-simple-maps 5.0.5
- Papa Parse 5.7.0
- JavaScript / JSX
- HTML5 / CSS3
- OpenRouter API for the Decision Intelligence feature


Primary analytical processing was performed using Python notebooks:

- Data_Cleaning_v5.ipynb
- Comment_Sentiment_Pipeline_v2.ipynb

No special desktop BI software is required to view the dashboard. A modern
web browser such as Google Chrome, Microsoft Edge, Firefox or Safari is
sufficient.


5.2 STEP-BY-STEP INSTRUCTIONS TO OPEN AND NAVIGATE THE DASHBOARD
================================================================

A. DEPLOYED VERSION

1. Open the provided dashboard URL in a modern browser.

2. Wait for the dashboard datasets to finish loading.

3. Use the top navigation menu:

   Overview
   -> States
   -> MarineWatch
   -> Forecast
   -> Impact Analysis
   -> Methodology

4. OVERVIEW
   - Review national sustainable-tourism KPIs.
   - Change the year range to inspect historical trends.
   - Review national sentiment and sustainability observations.
   - Use Decision Intelligence for evidence-grounded interpretation.

5. STATES
   - Select a state using the map, ranking or state selector.
   - The default selected state is Melaka.
   - Change the end year to select the STI/report-card year.
   - Review STI, pillars, year-on-year changes, recovery, stability and
     sentiment evidence.
   - Open Decision Intelligence for an explanation of the selected state.

6. MARINEWATCH
   - Filter marine monitoring stations by state, MWQI class, trend or
     station category.
   - Select an individual station to inspect its latest MWQI, historical
     measurements, five-year change, trend and monitoring priority.
   - Marine Protected Area information represents available reference
     coordinates rather than legal boundaries.
   - Use Decision Intelligence for water-quality or station-level briefs.

7. FORECAST
   - Select the states to display.
   - Review domestic visitor and environmental forecast tasks.
   - Compare model performance with the naive persistence baseline.
   - Review 2025 forecasts and available actual observations.
   - Use Decision Intelligence to interpret forecast reliability.

8. IMPACT ANALYSIS
   - Review the observational two-way fixed-effects model.
   - Inspect coefficient, uncertainty, p-value, confidence interval and
     panel coverage.
   - Results must not be interpreted as definitive causal proof.

9. METHODOLOGY
   - Review STI construction, forecast validation, sentiment methodology,
     impact-analysis methodology, MarineWatch rules, data provenance and
     limitations.

10. Use Reset Filters to return the dashboard to its default state where
    applicable.


B. LOCAL VERSION

Requirements:
- Node.js 22.12 or newer
- npm

Install dependencies:

    npm ci

Validate dashboard data:

    npm run check:data

Start the Decision Intelligence backend in Terminal 1:

    npm run server

Start the frontend in Terminal 2:

    npm run dev

Open:

    http://localhost:5173/

To create the production bundle:

    npm run build

To preview the production bundle:

    npm run preview

Then open:

    http://localhost:4173/


5.3 ADDITIONAL REQUIREMENTS / PLUGINS / ADD-ONS
==============================================

No browser plugins or add-ons are required.

The core dashboard uses committed runtime datasets and can display its normal
visualisations without an external runtime data service.

The Decision Intelligence feature additionally requires:

- an active backend API
- an internet connection from the backend
- a valid OpenRouter API key
- access to a compatible language model

For local development, the .env file should contain values such as:

    OPENROUTER_API_KEY=your_api_key
    OPENROUTER_MODEL=your_model
    PORT=3001

The OpenRouter API key must remain on the server and must never be exposed
through a VITE_ environment variable.

If the AI service is unavailable or its quota has been reached, the normal
dashboard remains usable but Decision Intelligence responses may be
temporarily unavailable.


5.4 LIMITATIONS, ASSUMPTIONS AND SPECIAL CONSIDERATIONS
=======================================================

1. Missing STI observations remain unavailable. They are not replaced by zero
   and are not artificially interpolated.

2. Full STI is displayed only where all required inputs exist. Where available,
   an Economic + Social fallback may be displayed for states without complete
   full-STI inputs. The fallback is not treated as a full STI score.

3. Public sentiment is kept separate from measured STI indicators and is not
   combined into a single artificial sustainability score.

4. Sentiment results reflect the available online review/comment dataset and
   should not be interpreted as a representative population survey.

5. Forecast models are evaluated against naive persistence baselines. A model
   that does not outperform the baseline should not be interpreted as providing
   strong additional predictive value.

6. Environmental forecast actuals for the latest forecast period may not yet
   be published.

7. Impact Analysis uses an observational state-year panel with state and year
   fixed effects. Statistical association does not establish definitive
   causation.

8. A statistically non-significant estimate does not prove that no relationship
   exists.

9. Marine monitoring stations are not evenly distributed across Malaysia.
   Station-level measurements should not automatically be generalised to an
   entire coastline or state.

10. MarineWatch trend and monitoring-priority categories are dashboard
    decision-support heuristics and are not official Department of Environment
    regulatory classifications.

11. Marine Protected Area distances refer to available MPA reference
    coordinates and not legal protected-area boundaries.

12. Decision Intelligence is evidence-grounded but AI-generated. It is intended
    to support human interpretation and should not replace expert or regulatory
    judgement.

13. Decision Intelligence availability depends on the configured AI provider,
    model availability, API quota and rate limits.

14. JavaScript must be enabled and a modern browser is recommended.


CURRENT ANALYTICAL SOURCES
==========================

Primary structured analysis:
    Data_Cleaning_v5.ipynb

Primary sentiment analysis:
    Comment_Sentiment_Pipeline_v2.ipynb

Data_Cleaning_v2.ipynb and scripts/export_dashboard.py are historical
artifacts and are not current dashboard inputs.


FINAL NAVIGATION
================

Overview
-> States
-> MarineWatch
-> Forecast
-> Impact Analysis
-> Methodology

Public sentiment is integrated into Overview and States rather than provided
as a separate navigation page.