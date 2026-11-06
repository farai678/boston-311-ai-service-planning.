# Boston 311 AI Service Planning Assistant

**Generative AI-powered complaint classification, demand forecasting, and workforce planning using real municipal service-request data.**

## Project Overview

This project was developed for IE 5374 Applied Generative AI at Northeastern University.

The Boston 311 AI Service Planning Assistant combines Generative AI and historical data analysis to explore how municipal governments can classify service requests, forecast future demand, and plan workforce capacity more efficiently.

The application allows users to enter a fictional resident complaint, receive an AI-generated service-request classification, and view department-level staffing forecasts and cost comparisons.

## Data Source

Historical service-request data for 2023 and 2024 were obtained from the City of Boston's [311 Service Requests Open Data](https://data.boston.gov/dataset/311-service-requests).

The analysis focuses on four departments:

- Public Works
- Transportation
- Parks and Recreation
- Inspectional Services

## System Architecture

**Resident complaint → OpenAI GPT-4.1-mini → Structured classification → Department review → Staffing plan lookup**

**Historical 311 data → Data cleaning → Monthly demand forecasting → Staffing simulation → Cost and backlog analysis**

The application combines these two workflows through an interactive interface built in Google Colab.

## Methodology

The project uses prompt engineering, OpenAI API integration, and structured JSON output to classify service complaints into approved historical request types.

Monthly 2025 demand is forecast using historical 2023–2024 request volumes and changes between the two years.

The staffing simulation estimates workforce requirements based on forecast demand, crew capacity, staffing costs, hiring delays, seasonal workers, and a selected crew-release scenario.

Sensitivity analysis tests how the staffing plans respond to demand changes of -20% and +20%.

## Key Results

| Metric | Result |
|---|---|
| AI exact-match accuracy | 90% (27 of 30 synthetic test cases) |
| Original annual staffing cost | $15,025,999.95 |
| Revised annual staffing cost | $14,979,333.33 |
| Estimated net savings | $46,666.62 |
| Additional baseline backlog from revision | 0 |

The revised staffing scenario releases four Inspectional Services crews effective September 2025, following notice in August.

Although the revised plan reduces costs under baseline demand, its December backlog increases from 145 to 1,489 requests for Inspectional Services when demand is 20% above forecast.

## Technologies Used

Python, Pandas, NumPy, scikit-learn, OpenAI API, GPT-4.1-mini, Matplotlib, ipywidgets, and Google Colab.

## How to Run

1. Open `IE5374 Boston311 AI Hackathon.ipynb` in Google Colab.
2. Download the official Boston 311 datasets for 2023 and 2024 and upload them when prompted by the notebook.
3. Add an `OPENAI_API_KEY` secret in Google Colab and enable notebook access.
4. Install the dependencies specified in the notebook and run its cells in order.
5. Use the interactive complaint classifier to enter fictional complaints and compare staffing scenarios.

OpenAI API access may incur usage charges. API keys must never be committed to the repository.

## Repository Contents

The repository includes the Jupyter notebook and six CSV result files containing demand forecasts, staffing plans, sensitivity analysis, request-type information, and AI evaluation results.

## Limitations

This project is a historical planning prototype, not an operational Boston 311 system.

The 2025 forecasts are estimates, not actual 2025 performance. The staffing model evaluates a baseline and selected cost-saving scenario rather than finding a globally optimal solution. It does not fully optimize individual service deadlines, late-service penalties, or all possible hiring and release decisions.

AI evaluation uses only 30 synthetic examples. Some service categories overlap, and the preliminary test results should not be interpreted as verified real-world accuracy.

Ambiguous department or queue assignments require human review.

## Development and AI-Use Disclosure

This project was completed individually.

Generative AI tools, including ChatGPT and the OpenAI API, were used to assist with project development, code generation, debugging, classification, and documentation.

The project author executed the code, reviewed outputs, tested the application, and interpreted the analytical results.

## Academic Context

IE 5374 — Applied Generative AI  
Northeastern University

**Project:** Boston 311 AI Service Planning Assistant
