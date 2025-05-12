# PyGrowthClean

A Python version of the [growthcleanr](https://github.com/carriedaymont/growthcleanr) package, which provides automated cleaning and standardization of pediatric growth data such as height and weight measurements.

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

