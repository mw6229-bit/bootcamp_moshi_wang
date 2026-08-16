# Bootcamp Repository

## Folder Structure
- **homework/** → All homework contributions will be submitted here.
- **project/** → All project contributions will be submitted here.
- **class_materials/** → Local storage for class materials. Never pushed to GitHub.

## Homework Folder Rules
- Each homework will be in its own subfolder (`homework0`, `homework1`, etc.)
- Include all required files for grading.

## Class Materials Rules
- Each stage's handouts go in their own subfolder, named exactly as the course folder, e.g. `class_materials/stage01_problem-framing-and-scoping/`.
- Run lecture notebooks in place from that folder.
- Copy a homework starter into `homework/homeworkN/` before working on it.

## Project Folder Rules
- Keep project files organized and clearly named.
- The project folder structure is set up in Stage 02.


# VIX Spikes and Its Downside Risk on S&P 500 
**Stage:** Problem Framing & Scoping (Stage 01)

## Problem Statement
Will spikes in VIX elevate the downside risk of S&P500 in the next trading day? 
VIX represents the option market's expectation of future market volatility, and usually increases when market stress increases. When VIX elevates, there is a possibility that the equity market will decline, therefore, we are trying to find if the relationship between VIX spikes and S&P500 is strong enough to predict the outcome.

## Stakeholder & User
Investors, traders, and portfolio managers will be the main stakeholders and users.

## Useful Answer & Decision
The answer should be predictive, and should use next day's S&P500 return as the metric. A useful answer would indicate the downside risk of the equity market on the next trading day. If the downside risk of the S&P 500 increases after VIX spikes, investors may use this information to decide whether they should lower their equity exposure and strengthen risk management. The final analysis will include the results and visualizations comparing market performance after VIX spikes with normal trading days.

## Assumptions & Constraints
- We assume that historical S&P500 and VIX are accurate and complete.
- We assume that historical data are sufficient enough to decide whether VIX spikes provide predictive information
- We need to define a threshold for identify VIX spikes

- Factors affecting S&P 500 are more than just VIX, therefore the outcome of the next trading day cannot simply be attributed to VIX effects
- The relationship between VIX and the S&P 500 may change under different market conditions

## Known Unknowns / Risks
- We do not know what threshold should be used to define a VIX spike. We can test different thresholds and compare the results
- We do not know whether the downside risk of the S&P 500 is actually higher after VIX spikes. We will compare the next-day returns after VIX spikes with normal trading days
- The relationship between VIX spikes and S&P 500 returns may change over time. We can compare the results from different time periods

## Lifecycle Mapping
- Define the research problem → Problem Framing & Scoping (Stage 01) → Project scoping paragraph
- Identify the stakeholders → Problem Framing & Scoping (Stage 01) → Stakeholder context
- Define the project scope → Problem Framing & Scoping (Stage 01) → Analysis plan

## Repo Plan
- data/ → Store VIX and S&P500 data
- src/ → Store Python scripts and functions used in the analysis
- notebooks/ → Store Jupyter notebooks for data analysis and visualization
- docs/ → Store project documentation and stakeholder materials
- The repository will be updated after each stage of the project