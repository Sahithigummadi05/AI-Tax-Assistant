# Tax Assistant System 2025

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

IRS-compliant tax calculation system with ML-powered deduction optimization for individual/joint filers.

## Features

- 📊 **2025 Tax Compliance**: Updated brackets/rates/deductions
- 🤖 **ML Optimization**: Decision Tree model for deduction strategy
- 👫 **Joint Filing**: Combined spouse income handling
- 📟 **CLI Interface**: User-friendly command-line workflow


## How Tax is Calculated

The system uses a progressive tax bracket system based on 2025 IRS projections. Here's a step-by-step explanation with examples:

### 1. Determine Taxable Income
Taxable Income = Gross Income - Deductions

### 2. Apply Tax Brackets
For each bracket, tax is calculated on the portion of income that falls within that bracket.

#### Example 1: Single Filer

Assume a single filer with $75,000 taxable income:

| Bracket     | Rate | Calculation                  | Tax      |
|-------------|------|------------------------------|----------|
| $0-$11,600  | 10%  | 11,600 × 10%                 | $1,160   |
| $11,601-$47,150 | 12% | (47,150 - 11,600) × 12%   | $4,266   |
| $47,151-$75,000 | 22% | (75,000 - 47,150) × 22%   | $6,127   |
| **Total Tax** |    |                              | **$11,553** |

#### Example 2: Married Filing Jointly

Assume a married couple filing jointly with $150,000 taxable income:

| Bracket     | Rate | Calculation                  | Tax      |
|-------------|------|------------------------------|----------|
| $0-$23,200  | 10%  | 23,200 × 10%                 | $2,320   |
| $23,201-$94,300 | 12% | (94,300 - 23,200) × 12%   | $8,532   |
| $94,301-$150,000 | 22% | (150,000 - 94,300) × 22% | $12,254  |
| **Total Tax** |    |                              | **$23,106** |

### 3. Deduction Optimization
The ML model predicts whether itemizing deductions would be more beneficial than taking the standard deduction. This decision is based on:
- Mortgage interest
- Charitable donations
- Medical expenses (above 7.5% AGI threshold)

### 4. Final Tax Calculation
Tax Owed = Calculated Tax - Credits (if applicable)

## Project Structure

| File/Folder       | Description                          |
|--------------------|--------------------------------------|
| `tax_system.py`    | Main application logic               |
| `TaxCalculator`    | IRS bracket calculations             |
| `DeductionOptimizer` | ML model for deduction strategy    |
| `tests/`           | Unit test suite                      |
| `tax_system.log`   | System logs                         |

## ML Implementation

**Model**: Decision Tree Classifier  
**Features**:
- Income
- Mortgage interest
- Charity donations
- Medical expenses
- Filing type (0=single, 1=married, 2=joint)

**Training Data**: 10,000 synthetic tax filings

## Security

- AES-256 encryption for all financial data
- Input validation/sanitization
- Secure logging practices

## Testing


Sample test cases included for:
- Bracket boundary conditions
- Zero-income handling
- Joint filing validation


## License

Distributed under MIT License. See `LICENSE` for details.

## Acknowledgments

- IRS Publication 17 for tax guidelines
- Scikit-learn ML ecosystem
- Python Cryptography Toolkit

---

