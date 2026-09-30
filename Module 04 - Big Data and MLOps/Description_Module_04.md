# Big Data and MLOps Framework

This repository contains the syllabus, implementation steps, and structural guidelines for the Big Data and MLOps module. The curriculum progresses from distributed data processing with PySpark and relational persistence, to parallel processing with Dask and NoSQL cloud storage, to professional software quality practices, and finally to deploying machine learning models as containerized APIs.

---

## Week 1: Big Data Workshop — Distributed Queries and Large Volumes

### Formative Activity: Building a Distributed Data Pipeline
The goal is to build a data pipeline that extracts massive amounts of information, processes it in a distributed fashion with PySpark, and persists the analytical results in a MySQL relational database.

### Phase 1: Environment Setup and Extraction
*   **Installation:** Setting up `pyspark` and `mysql-connector-python`.
*   **Data Loading:** Importing a CSV dataset of transactions or logs with a minimum of 50,000 records.
*   **Spark Session:** Initializing an optimized `SparkSession` with a descriptive application name.

### Phase 2: Distributed Processing with PySpark
**Transformations and Aggregations:**
*   Defining or inferring the schema and cleaning null or inconsistent values.
*   Creating calculated columns (e.g., "Total with Taxes") and applying advanced filters.
*   Running `groupBy` operations to obtain key metrics (averages, counts per hour).

### Phase 3 and 4: MySQL Persistence and Validation
**Output Flow:**
*   **Connection:** Establishing a secure link from Python to MySQL.
*   **Modeling:** Creating the specific table that will receive the processed results.
*   **Load and Query:** Inserting data using prepared statements and running a final `SELECT` to confirm successful persistence.

### Submission Format (Moodle)
1.  **Notebook (`.ipynb`):** Well-organized code with technical documentation.
2.  **Screenshots:** Evidence of the MySQL table with the inserted data (Workbench or terminal).

---

## Week 2: NoSQL Practice — Python Integration and Parallel Processing

### Collaborative Graded Activity
Teams of 3 members design a workflow that processes Big Data and stores it in a scalable NoSQL database.

### Phase 1: Teams and Strategic Roles
*   **Data Engineer:** Dask logic and data cleaning.
*   **NoSQL DBA:** MongoDB / Cassandra.
*   **Cloud Architect:** AWS / GCP connectivity.

### Phase 2: Massive Processing with Dask
Using `dask.dataframe` to operate on a dataset that exceeds conventional RAM, performing aggregations and advanced filters.

**Key Evaluation Point:** Documenting the execution time comparison between Pandas (sequential) and Dask (parallel).

### Phase 3: Persistence and Cloud Queries
*   **Export:** Sending the processed results to a MongoDB Atlas instance or similar.
*   **Querying:** Running at least 3 complex queries (filters, sorting, limits) that validate the efficiency of the NoSQL engine.

### Submission Format (Moodle)
1.  **Files:** Each team member uploads the file or a link to the repository.
2.  **Report (PDF):** Includes screenshots of the Cloud infrastructure (AWS/GCP) in operation.

---

## Week 3: Quality Workshop — Unit Testing and Professional Documentation

### Formative Activity: From Script to Engineering Product
A data analysis that cannot be reproduced or tested has no real value. In this activity, a conventional script is transformed into a project that follows professional software standards.

### Phase 1: Structure and Version Control
**Repository Setup:**
*   Creating the `taller_calidad_semana15` folder and initializing it with `git init`.
*   Configuring a `.gitignore` file to exclude `__pycache__/` and `.csv` files.
*   Organizing the directory with `data/`, `src/`, and `tests/` folders.

### Phase 2: Logic and Documentation (Docstrings)
Developing `src/procesamiento.py` with the function `calcular_metricas_ventas(dataframe)`.

**Mandatory Requirement:** Including a Docstring (Google or NumPy style) detailing the parameters, data types, and purpose of the function.

### Phase 3: Unit Testing with Pytest
Creating `tests/test_procesamiento.py` with at least two tests:
*   **Calculation Test:** Verifies that the sales total is correct using known data.
*   **Empty Test:** Evaluates how the function reacts to a DataFrame with no records.

### Submission Format (Moodle)
1.  **Dependencies:** A `requirements.txt` file (pandas, pytest).
2.  **Project Archive:** The project compressed as a `.ZIP`, including the hidden `.git` folder so the commit history can be validated.

---

## Week 4: MLOps Lab — Deployment with API and Docker

### Graded Activity: From Static Model to Production Service
Building an Application Programming Interface (API) that serves real-time predictions, and packaging the solution in a Docker container to guarantee portability.

### Phase 1 and 2: Preparation and API Development
*   **Serialization:** Exporting the trained model to a `model.pkl` file using `joblib` or `pickle`.
*   **FastAPI / Flask:** Creating `main.py` and defining the input structure with Pydantic to validate data (age, income, etc.).
*   **Endpoint:** Implementing the `POST /predict` method to receive JSON and return the model's prediction.

### Phase 3 and 4: Environment and Dockerization
**Dockerfile Recipe:**
1.  Use a Python base image and set `/app` as the working directory.
2.  Copy and install `requirements.txt` (fastapi, uvicorn, scikit-learn).
3.  Copy the code and `model.pkl`.
4.  Expose a port (e.g., 8000) and define the startup command.

### Phase 5: Local Testing
Running the following commands to validate the solution:
*   `docker build -t ml-api-app .`
*   `docker run -p 8000:8000 ml-api-app`
*   Verifying it works in Swagger at `http://localhost:8000/docs`.

### Submission Format (Moodle)
A `.zip` or `.rar` file containing: `main.py`, `model.pkl`, `requirements.txt`, and `Dockerfile`. (Optional: `README.txt`).
