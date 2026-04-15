🧭 User Journey Funnel Analysis

A data analysis project exploring how users navigate an e-learning website — identifying drop-off points, conversion bottlenecks, and actionable UX improvements.

Author: Ghaith Hajji — IT Student at TBS & Data Science Enthusiast
Dataset: 9,935 sessions · 1,350 unique users · 3 subscription types

📌 Project Overview
This project analyses raw user session data from an e-learning platform to answer a core business question:

Where are users dropping off, and what can be done to improve the conversion funnel?

Using Python, Pandas, and Plotly, the project traces user journeys from first page visit through to checkout, quantifies drop-off rates at every stage, and produces a business-ready PDF report with prioritised recommendations for the UX and product teams.

📁 Repository Structure
├── user_journey_raw.csv        # Raw dataset (sessions, journeys, subscription types)
├── funnel_analysis.py          # Main analysis script (all charts + printed summary)
├── generate_report.py          # PDF report generation script (ReportLab)
├── User_Journey_Funnel_Analysis_Report.pdf   # Final business report
└── README.md                   # You are here

📊 Dataset
ColumnTypeDescriptionuser_idintUnique identifier per usersession_idintUnique identifier per sessionsubscription_typestrAnnual, Monthly, or Quarterlyuser_journeystrDash-separated sequence of pages visited (e.g. Homepage-Pricing-Checkout)
Pages tracked: Homepage, Pricing, Sign up, Log in, Checkout, Courses, Career tracks, Career track certificate, Course certificate, Resources center, Instructors, Coupon, About us, Upcoming courses, Blog, Success stories, Other

🔍 Key Findings
MetricValueStatusBounce rate (single-page sessions)64.2%🔴 CriticalSessions reaching Checkout20.3%🟠 Needs attentionCheckout abandonment rate96.4%🔴 CriticalPricing → Checkout conversion26.4%🟠 Needs attentionSessions with purchase intent37.7%🔵 BaselineCoupon page drop-off rate98.8%🔴 Critical
Top Drop-off Points

Coupon — 98.8% of visits end the session (broken/expired coupon experience)
Checkout — 94.4% drop-off (friction in the payment flow)
Log in — 93.7% drop-off (authentication issues and repeated login loops)

Most Common Journey Patterns
RankJourney% of Sessions1Log in only22.7%2Checkout only17.8%3Other only10.2%4Coupon only10.1%5Homepage → Log in8.5%

🛠️ How to Run
1. Clone the repository
bashgit clone https://github.com/VECTORZ24/User-Journey-Funneal-Analysis.git
cd user-journey-funnel-analysis
2. Install dependencies
bashpip install pandas plotly reportlab
3. Run the analysis
bashpython funnel_analysis.py
This will open 12 interactive Plotly charts in your browser and print the full summary to the console.
4. Generate the PDF report
bashpython generate_report.py
This produces User_Journey_Funnel_Analysis_Report.pdf in the current directory.

⚠️ Make sure user_journey_raw.csv is in the same directory as the scripts before running.


📈 Analysis Breakdown
Data Cleaning

Journey strings are parsed from dash-separated format into ordered page lists
Consecutive duplicate pages are removed (e.g. Log in-Log in-Log in → Log in) to eliminate refresh loops and surface true navigation intent

Analyses Performed
#AnalysisMethod1Page visit frequencyValue counts across all deduplicated journeys2Entry & exit page distributionFirst/last page extraction per session3Conversion funnelSessions reaching each stage of Homepage → Checkout4Funnel by subscription typeGrouped analysis per Annual / Monthly / Quarterly5Post-Pricing behaviourNext page after Pricing page visit6Post-Sign up behaviourNext page after Sign up page visit7Checkout abandonmentSessions exiting on Checkout page8Per-page drop-off rateExit count / appearance count per page9Page transition matrix12×12 probability heatmap of page-to-page navigation10Top journey patternsMost frequent deduplicated session sequences

💡 Recommendations Summary
PriorityAreaAction🔴 CriticalCheckout flowFull UX audit, add trust signals, implement exit-intent capture🔴 CriticalAuthenticationFix login loops, add social login, simplify password reset🟠 HighCoupon experienceValidate coupon codes in real-time, surface discounts proactively🟠 HighPricing page CTAAdd prominent CTA, plan comparison table, and social proof🔵 MediumPage trackingTag all "Other" pages to gain visibility into 10%+ of sessions

📄 Report
The full business report (User_Journey_Funnel_Analysis_Report.pdf) includes:

Executive summary with stakeholder-oriented narrative
KPI dashboard with severity indicators
Visual funnel diagram and annotated tables
Page-level drop-off bar charts
Subscription type breakdown
Top 15 journey pattern analysis
Prioritised UX recommendations with targets


🧰 Tech Stack
ToolPurposePython 3Core languagePandasData loading, cleaning, and analysisPlotlyInteractive charts and visualisationsReportLabPDF report generationitertools.groupbyConsecutive duplicate removal

👤 Author
Ghaith Hajji
IT Student at TBS (Tunis Business School) & Data Science Enthusiast
