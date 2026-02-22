
# 🏗️ Project Thesis: An ESG Data Support Engine (Simulation)

An automated, 6-phase data analytics containerised pipeline for aggregating multidimensional GHG data.


The goal of my project is to create a simulation that replicates the "Data Engines" ESG teams use in the real world. I am building this project as a learning process to develop an automated ingestion pipeline based on the Google Analytics 6-Phase Lifecycle (Ask, Prepare, Process, Analyse, Share, Act). It is designed to simulate the automation of cleaning, processing, and aggregating raw Greenhouse Gas (GHG) data from synthetic datasets.

Multidimensional data collection is  susceptible to formatting inconsistencies and complexity. To solve this, I'm building a validation gateway that automatically highlights errors and standardises unit measurements. The engine processes multidimensional environmental data in O(N) time using vectorised Pandas operations, logs it to a local PostgreSQL database, and delivers outputs into a stakeholder-ready Excel summary. This ensures that the data is accurate, mathematically sound, and ready for stakeholder review.

# Project Purpose: A Technical Portfolio

I am building this automated 6-phase data pipeline specifically to demonstrate my readiness for Customer Success and Implementation roles within the ESG software sector.
For growing companies, navigating new regulations like the CSRD can be overwhelming. A mid-sized firm might have 15 years of operational data—like diesel receipts and electricity bills—but when regulators or investors suddenly demand fully auditable Scope 1, 2, and 3 emissions, that fragmented data becomes a massive liability. They rarely have dedicated ESG departments; they have stressed operations managers and messy spreadsheets.

This simulation acts as my technical proof of concept. It demonstrates how I would bridge the gap between a client's messy operational reality and a clean, compliant SaaS environment. 

By automating the data analytics lifecycle, this project highlights my ability to:

- **Translate & Process**: Synthesise and standardise operational metrics (e.g., converting "gallons of diesel" to "tonnes of $CO_2e$") efficiently at scale.

- **Consolidate & Share**: Aggregate complex metrics into a secure database, delivering clear, auditable summaries that relieve operational anxiety and empower companies to optimise processes and get leaner.

# The Operational Strategy
This pipeline acts as an automated "Engine" for ESG reporting. It ingests raw .xlsx and .csv files, validates the data against physical environmental realities, processes the maths via vectorised transformations, and stores outputs in a PostgreSQL database. 

It transforms fragmented data into a hassle-free, seamless collection process—mitigating the bottlenecks of traditional spreadsheet processing:

1. **Ask & Prepare**: 
Data collection through a custom Synthetic Generator and kaggle ESG dataset (https://www.kaggle.com/datasets/tunguz/environment-social-and-governance-data)

3. **Process** (The Validation Gateway): 
Handled by a Dockerised Python pipeline. At the point of ingestion, a Pydantic gateway standardises unit measurements and highlights inaccurate fields to ensure data integrity before it reaches the analysis stage.

5. **Analyse & Share** (Vectorised Aggregation): 
Using O(N) Vectorized Pandas operations, the engine aggregates millions of rows in milliseconds—bypassing the bottlenecks of traditional spreadsheets. The "Analyse" phase produces real-time completion metrics, while the "Share" phase delivers stakeholder-ready Excel summaries and logs for auditability.


**The Synthetic Reliability Test** 

To guarantee system reliability, the pipeline's construct validity will be stress-tested against a custom Python generator. This script generates 50 synthetic, multi-company Excel files deliberately injected with "faulty" data (comprising unit errors, invalid data types, missing IDs, and negative emissions). This proves the Pydantic gatekeeper can successfully quarantine 100% of anomalies while maintaining an auditable logging trail.



# **Core Engineering Principles**:
I am using this project as a foundation to build the skills and tools listed below. 

- **Construct Validity (Pydantic)**: At the ingestion point, data is fed through a validation gate. If data exceeds given parameters, it is logged, protecting the downstream SQL database from errors.
- **Vectorized Processing (Pandas)**: As a challenge to myself, standard iterative loops will be superseded in favour of C-optimised, vectorised .groupby() operations. This reduces aggregation time from hours to milliseconds.
- **Environment Isolation (Docker)**: I am learning to build the Python processor and the PostgreSQL database so they are fully containerised and networked via Docker Compose.
- **Auditability (logging)**: Uses the standard Python logging module to create a permanent, timestamped audit trail of all data anomalies, system states, and database transactions.
