
# 🏗️ An ESG Data Support Engine (Simulation)

An automated, 6-phase data analytics containerised pipeline for aggregating multidimensional data.

The goal is to create a simulation that replicates the "Data Engines" ESG teams use in the real world. 


# Project Purpose: A Technical Portfolio

Based on the Google Analytics 6-Phase Lifecycle (Ask, Prepare, Process, Analyse, Share, Act). I am building this automated 6-phase data pipeline to demonstrate my technical readiness for Customer Success roles within the Environmental software sector - Geospatial analyst (GIS).


# The Operational Strategy
This pipeline mimics an automated "Engine" for ESG reporting. It ingests raw .xlsx and .csv files, validates the data against physical environmental realities, processes the maths via vectorised transformations, and stores outputs in a PostgreSQL database. 

It transforms fragmented data into a hassle-free, seamless collection process—mitigating the bottlenecks of traditional spreadsheet processing:

-  **Ask & Prepare**:
To guarantee system reliability, the pipeline's construct validity will be stress-tested against a custom Python generator. This script generates 50 synthetic, multi-company Excel files deliberately scrambled and injected with random faulty data, as a challenge to prove the Pydantic gatekeeper and pipeline can successfully digest, synthesise and aggregate 100% of anomalies within the parameters of it's logic.

- **Process** (The Validation Gateway): 
Handled by a Dockerised Python pipeline. At the point of ingestion, a Pydantic gateway standardises unit measurements and highlights erorrs to ensure data integrity before it reaches the analysis stage.

- **Analyse & Share** (Vectorised Aggregation): 
Using O(N) Vectorised Pandas operations, the engine aggregates millions of rows in milliseconds—bypassing the bottlenecks of traditional spreadsheets. The "Analyse" phase produces real-time completion metrics, while the "Share" phase delivers stakeholder-ready Excel summaries.



# **Core Engineering Principles**:
I am using this project as a foundation to build the skills and tools listed below. 

- **Construct Validity (Pydantic)**: At the ingestion point, data is fed through a validation gate. If data exceeds given parameters, it is logged, protecting the downstream SQL database from errors.
- **Vectorized Processing (Pandas)**: As a challenge to myself, standard iterative loops will be superseded in favour of C-optimised, vectorised .groupby() operations. This reduces aggregation time from hours to milliseconds.
- **Environment Isolation (Docker)**: I am learning to build the Python processor and the PostgreSQL database so they are fully containerised and networked via Docker Compose.
