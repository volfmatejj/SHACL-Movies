# SHACL Movie Validation Project

This repository contains all files related to a semester project focused on
validating movie data using SHACL and the DBpedia ontology.

## Project Overview

The goal of this project is to design and test a SHACL shape graph that validates
RDF data describing movies (`dbo:Film`). The validation focuses on identifying
missing core attributes, incorrect data types, and incomplete semantic descriptions.

The descriptive part of the project is submitted separately via the university system.
This repository serves as the technical implementation of the project.

## Repository Contents

All files are stored in the root of the repository:

- `shapes_movies_en.ttl` – SHACL shape graph defining validation rules for movies
- `movies_en.ttl` – RDF dataset extracted from DBpedia using a SPARQL CONSTRUCT query
- `data_synthetic_valid.ttl` – synthetic dataset containing only valid movie records
- `data_synthetic_errors.ttl` – synthetic dataset designed to trigger validation errors
- `extract_movies.sparql` – SPARQL query used to extract movie data from DBpedia
- `validation_real_data.txt` – validation report for real-world DBpedia data
- `validation_synthetic_errors.txt` – validation report for synthetic error data

## Tools Used

- DBpedia SPARQL endpoint (https://dbpedia.org/sparql)
- SHACL Playground (https://shacl.org/playground/)





