# PyGrowthClean

A Python version of the [growthcleanr](https://github.com/carriedaymont/growthcleanr) package, a tool for automatically cleaning and standardizing pediatric growth data such as height and weight. It detects implausible measurements by analyzing each patient's growth over time and comparing it to established pediatric growth charts. 

Each measurement is flagged as either valid or implausible, with specific codes explaining why a value was excluded. All original data remains intact—only a new column of flags is added—so researchers can decide which measurements to include or exclude in their studies of EHR growth data.

This package implements the growth cleaning algorithm developed by Daymont et al., as detailed in Supplemental File 3 of their published paper:

>Carrie Daymont, Michelle E. Ross, A. Russell Localio, Alexander G. Fiks, Richard C. Wasserman, Robert W. Grundmeier. Automated identification of implausible values in growth data from pediatric electronic health records. Journal of the American Medical Informatics Association, Volume 24, Issue 6, November 2017, Pages 1080–1087. https://doi.org/10.1093/jamia/ocx037.

It also includes a Python version of the CDC's SAS macro for calculating pediatric growth percentiles and z-scores.

## Features
- Implements logic for identifying outliers in height and weight data
- Filters and flags implausible or erroneous measurements
- Comes with unit tests for core functionality

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/growthcleanr-python.git
cd PyGrowthClean
```

Install in development mode:

```bash
pip install -e .
```

## Usage

### Basic Example

```python
from growthcleanr.cleaner import clean_growth_data

# Sample data: list of dicts or load from CSV/DF
data = [
    {"id": 1, "age": 5.5, "sex": "M", "height": 110.0, "weight": 18.0},
    {"id": 2, "age": 6.0, "sex": "F", "height": 115.0, "weight": 20.0},
]

cleaned = clean_growth_data(data)
print(cleaned)
```

### CLI Example

```bash
growthcleanr --input data.csv --output cleaned.csv
```

## Repository Structure

```
PyGrowthClean/
├── growthcleanr/     # Core Python package
├── tests/            # Unit tests
├── examples/         # Example notebooks
```


## Credits

- Original algorithm: [growthcleanr R package](https://github.com/carriedaymont/growthcleanr) by Carrie Daymont

