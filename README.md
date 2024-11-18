# Forward Firm Universe Analysis

This project focuses on identifying and cleaning duplicate firm names in the Forward Firm Universe dataset. These duplicates arise from variations in spellings or suffixes (e.g., LTD, PLC, Corp). The project uses advanced data cleaning and matching techniques, including AI and text similarity, to standardize and enhance the dataset.

---

## Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [Approach](#approach)
4. [Steps Performed](#steps-performed)
5. [Key Statistics](#key-statistics)
6. [Requirements](#requirements)
7. [Usage](#usage)
8. [Results](#results)

---

## Overview

The goal of this project is to process the Forward Firm Universe dataset to:
1. Identify duplicate firm names caused by variations in suffixes or spellings.
2. Match firms with their respective Legal Entity Identifier (LEI) data.
3. Provide a clean and augmented dataset for downstream applications.

---

## Features

- **Automated LEI Data Download and Parsing**:
  - Downloads the latest LEI data from [GLEIF](https://leidata.gleif.org).
  - Extracts LEI records and stores them in a SQLite database.

- **Firm Name Standardization**:
  - Normalizes firm names by removing suffixes and standardizing text.

- **Similarity Matching**:
  - Uses cosine similarity and clustering to identify duplicates and variations in firm names.

- **Data Augmentation**:
  - Matches firm names with LEI records and updates the dataset with LEI codes.
  - Match firm names with People Data Labs records and updates the dataset accordingly.

---

## Approach

1. **Data Acquisition**:
   - LEI data is downloaded in XML format and parsed into a structured SQLite database.
   - The Forward Firm Universe dataset is loaded from an Excel file for processing.

2. **Standardization**:
   - Firm names are cleaned and normalized by:
     - Converting to lowercase.
     - Removing suffixes like "LTD", "PLC", and "Corp".
     - Stripping special characters.

3. **Similarity Matching**:
   - Cosine similarity is applied to compare firm names.
   - High-similarity matches are clustered to identify duplicates or variations.

4. **Integration**:
   - Augmented the Excel dataset with LEI codes and similarity scores.
   - Provided additional metadata for further analysis.

---

## Steps Performed

### Step 1: LEI Data to Database
- **Download and Unzip**:
  - Automated downloading of LEI XML data from the GLEIF API.
  - Extracted the XML file and renamed it for further processing.
- **Parsing**:
  - Extracted key fields like LEI code, firm name, and additional metadata.
- **Database Storage**:
  - Stored LEI records in a SQLite database for efficient querying.

### Step 2: Firm Name Cleaning and Matching
- **Excel Data Loading**:
  - Loaded the Forward Firm Universe dataset from Excel.
- **Data Cleaning**:
  - Normalized firm names by removing suffixes and applying text standardization.
- **Clustering and Matching**:
  - Applied cosine similarity to detect and group similar firm names.
  - Compared cleaned firm names against the LEI database.
- **Augmentation**:
  - Updated the dataset with LEI codes LEI database and People Data Labs API, similar ity scores, and duplicate group indices.

---

## Key Statistics

- **Number of Firms in LEI Database**: 2769569
- **Number of Firms in Excel Dataset**: 162
- **Matches Found**: 8164
- **Duplicates Identified**: Fuzzy Match

---

## Requirements

- Python 3.x

---

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/forward-firm-universe.git
   cd forward-firm-universe