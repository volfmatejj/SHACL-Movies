# SHACL Validation of Movie Data (DBpedia)

This repository contains the final project for the course **Grafová data a znalosti**.
The goal of the project is to design and evaluate a **SHACL shape graph** for validating RDF data
in the **movie domain**, based on the **DBpedia ontology**.

The project focuses on validating entities of type `dbo:Film` and demonstrates how SHACL
can be used to detect missing, inconsistent, or low-quality data in open knowledge graphs.

---

## Repository Contents

### SHACL Shapes
- **`shapes_movies_en.ttl`**  
  SHACL shape graph defining validation rules for `dbo:Film`.
  The shapes are divided into:
  - **Hard constraints (Violations)** – required structure and data types
  - **Soft constraints (Warnings)** – recommended completeness and semantic quality

---

### Data Files

- **`movies_en.ttl`**  
  Real-world movie data extracted from DBpedia using a SPARQL CONSTRUCT query.

- **`movies_en_synthetic_valid.ttl`**  
  Synthetic dataset with correctly structured movie entities.
  Used to verify that valid data passes validation without errors.

- **`movies_en_synthetic_errors.ttl`**  
  Synthetic dataset containing intentionally incorrect or incomplete movie records.
  Used to test individual SHACL rules (missing label, invalid runtime, wrong datatype, etc.).

---

### SPARQL

- **`SPARQL Query.txt`**  
  The SPARQL CONSTRUCT query used in the DBpedia SPARQL endpoint to extract movie data.

---

### Validation Reports

- **`Validation_Synthetic_Errors.txt`**  
  Validation report generated from the synthetic error dataset.

- **`Validation Report_Real data.txt`**  
  Validation report generated from real-world DBpedia movie data.

---

### Documentation

- **`SHACL - Movies.docx`**  
  Final written report describing the domain analysis, SHACL design,
  validation strategy, and interpretation of results.

---

## Validation Design Overview

### Core Constraints (Violations)
These rules define the minimum required structure of a movie entity:
- At least one English `rdfs:label`
- At least one `dbo:director` represented as an IRI
- Numeric `dbo:runtime` within a realistic range
- `dbo:releaseDate`, if present, must be single-valued and correctly typed

Violations indicate **structurally invalid data**.

---

### Advanced Constraints (Warnings)
These rules focus on data completeness and semantic quality:
- Directors and actors are recommended to be typed as `dbo:Person`
- At least one `dbo:genre` represented as an IRI is recommended
- `dbo:budget` should be present and single-valued

Warnings do not invalidate the data but highlight potential data quality issues,
which are common in open linked data sources such as DBpedia.

---

## Tools Used

- **DBpedia SPARQL Endpoint** – https://dbpedia.org/sparql  
- **SHACL Playground** – https://shacl.org/playground/

---

## Reproducing the Validation

1. Load one of the RDF data files (`movies_en.ttl` or a synthetic dataset).
2. Load the SHACL shapes file (`shapes_movies_en.ttl`).
3. Run SHACL validation using a SHACL-compatible tool.
4. Inspect the generated validation report.

---

## Author

**Matěj Volf**  
Prague University of Economics and Business  
Course: Grafová data a znalosti
