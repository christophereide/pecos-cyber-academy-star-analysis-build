# Pecos Cyber Academy STAR Longitudinal Pipeline (BigQuery)

This project builds a clean longitudinal STAR assessment dataset in BigQuery and produces student-level and aggregate growth tables for analysis.

## Overview

The pipeline ingests STAR exports from Google Cloud Storage (GCS), standardizes the fields into a reusable longitudinal format, and computes academic growth across testing windows:

- `BOY -> MOY`
- `BOY -> EOY`
- `MOY -> EOY`

It supports:

1. Growth by subject and grade level (school year summaries)
2. Growth by subject and cohort (graduation year)
3. Year-over-year cohort comparison for `BOY -> MOY`

## Data Sources

Assessment source:
- `STAR`

Current coverage:
- `SY 2024-25`: BOY, MOY, EOY (Math + Reading)
- `SY 2025-26`: BOY, MOY (Math + Reading)

## GCS Folder Structure

Recommended raw layout:

```text
gs://pecos-cyber-academy/longitudinal/
  assessment=star/
    sy=2024-25/
      subject=math/window=BOY/
      subject=math/window=MOY/
      subject=math/window=EOY/
      subject=reading/window=BOY/
      subject=reading/window=MOY/
      subject=reading/window=EOY/
    sy=2025-26/
      subject=math/window=BOY/
      subject=math/window=MOY/
      subject=reading/window=BOY/
      subject=reading/window=MOY/
