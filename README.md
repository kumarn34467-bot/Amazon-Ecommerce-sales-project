# Amazon Ecommerce Sales Analysis

## 1. Project Overview

This project analyzes the provided Amazon ecommerce order dataset using Python. It turns raw order records into validated sales metrics, summary tables, and visualizations.

The analysis covers:

- Sales and order trends
- Products, categories, and brands
- Customers and sellers
- Discounts, tax, and shipping
- Payment methods and order status
- Country, state, and city performance
- Data quality and total-amount validation

## 2. Project Objectives

The project is designed to answer these questions:

1. How much revenue and how many units were recorded?
2. Which products, categories, and brands perform best?
3. Which customers and sellers generate the most value?
4. How do sales change over time and across locations?
5. Which payment methods and order statuses are most common?
6. Are discounts associated with different order values?
7. Is `TotalAmount` consistent with the other financial fields?

## 3. Project Structure

```text
ECOMMERCE SALES PROJECT (2)/
|
|-- Amazon Ecommerce Dataset.csv
|-- Amazon_Ecommerce_Analysis.ipynb
|-- Amazon_Ecommerce_Project_Report.docx
|-- README.md
`-- requirements.txt
```

### File Responsibilities

| File | Responsibility |
| --- | --- |
| `Amazon Ecommerce Dataset.csv` | Original source data. This file is read-only. |
| `Amazon_Ecommerce_Analysis.ipynb` | Main executable analysis, tables, validation checks, and charts. |
| `requirements.txt` | Python packages required to run the notebook. |
| `Amazon_Ecommerce_Project_Report.docx` | Written explanation of the project, methodology, assumptions, and deliverables. |
| `README.md` | Project documentation and setup instructions. |

## View Dataset

[View Amazon Ecommerce Dataset](Amazon%20Ecommerce%20Dataset.csv)

Keep this README and `Amazon Ecommerce Dataset.csv` in the same folder when submitting the project.

## 4. How the Files Connect

```text
requirements.txt
	|
	v
Amazon_Ecommerce_Analysis.ipynb <---- Amazon Ecommerce Dataset.csv
	|
	+---- data-quality results
	+---- KPI tables
	+---- charts
	|
	v
Amazon_Ecommerce_Project_Report.docx
```

The notebook reads the CSV using the relative path `Amazon Ecommerce Dataset.csv`. The packages listed in `requirements.txt` provide the notebook's Python environment. The notebook outputs support the findings and recommendations documented in the Word report.

## 6. Requirements

- Python 3.9 or newer
- VS Code with the Jupyter and Python extensions, or Jupyter Notebook/Lab
- The CSV, notebook, and requirements file kept in the same project folder

## 7. Installation and Setup

From the project folder, run:

```bash
python -m venv .venv
```

On Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
jupyter notebook
```

Alternatively, open the project folder in VS Code, select the `.venv` Python interpreter, open the notebook, and select the same environment as its kernel.

## 8. Running the Analysis

1. Open `Amazon_Ecommerce_Analysis.ipynb`.
2. Select the Python environment where `requirements.txt` was installed.
3. Run the notebook cells from top to bottom.
4. Review the data-quality results before interpreting the KPIs.
5. Use the tables and charts when completing or presenting the project report.

The notebook performs transformations on an in-memory copy of the data. It does not overwrite, rename, or delete the source CSV.

## 9. Analysis Workflow

### Step 1: Load and inspect

- Load the CSV with pandas.
- Review shape, columns, data types, missing values, and unique values.
- Check duplicate rows and duplicate `OrderID` values.

### Step 2: Validate and prepare

- Convert `OrderDate` to a date.
- Convert financial fields to numeric values.
- Check negative or invalid values.
- Compare the recorded `TotalAmount` with a calculated amount.

### Step 3: Create features

- Year
- Quarter
- Month
- Discount amount
- Order value excluding tax and shipping

### Step 4: Analyze performance

- Overall KPIs
- Monthly sales
- Category and brand summaries
- Product rankings
- Customer and seller rankings
- Payment and order-status summaries
- Country and state summaries

### Step 5: Visualize and interpret

- Monthly sales trend chart
- Sales by category chart
- Sales by payment method chart
- Sales by country chart
- Summary tables for business interpretation

## 10. Dataset Fields

| Field Group | Fields |
| --- | --- |
| Order | `OrderID`, `OrderDate`, `OrderStatus` |
| Customer | `CustomerID`, `CustomerName` |
| Product | `ProductID`, `ProductName`, `Category`, `Brand` |
| Financial | `Quantity`, `UnitPrice`, `Discount`, `Tax`, `ShippingCost`, `TotalAmount` |
| Payment | `PaymentMethod` |
| Location | `City`, `State`, `Country` |
| Seller | `SellerID` |

## 11. Important Assumptions

- Each row is treated as one order record unless further investigation proves it represents a line item.
- `TotalAmount` is treated as the recorded sales value.
- Delivered, shipped, pending, cancelled, and returned orders are reported separately.
- Profit and margin are not calculated because cost-of-goods data is not included.
- The dataset is analyzed as provided; no source records are edited.

## 12. Troubleshooting

### File not found

Keep `Amazon Ecommerce Dataset.csv` in the same folder as the notebook. The notebook expects this exact filename.

### Module not found

Activate the correct Python environment and run:

```bash
pip install -r requirements.txt
```

Then select that same environment as the notebook kernel.

### Cells run out of order

Restart the notebook kernel and use **Run All**. The analysis cells depend on variables created by earlier cells.

## 13. Reproducibility and Data Protection

Keep all project files in one folder. If the CSV filename or location changes, update the notebook's `DATA_PATH` and this README together. The source CSV must remain unchanged; all cleaning and feature engineering happen in memory.

## 14. Deliverables

- Executable analysis notebook: `Amazon_Ecommerce_Analysis.ipynb`
- Dependency list: `requirements.txt`
- Project report: `Amazon_Ecommerce_Project_Report.docx`
- Project documentation: `README.md`

## 15. Separate Submission Checklist

Submit these files separately using the exact filenames below:

1. `Amazon Ecommerce Dataset.csv`
2. `Amazon_Ecommerce_Analysis.ipynb`
3. `requirements.txt`
4. `Amazon_Ecommerce_Project_Report.docx`
5. `README.md`

For the notebook to run, place the CSV in the same folder as the notebook. The notebook checks for all five project files when it starts and reports missing companion files. Do not rename the CSV or notebook unless you also update the `DATA_PATH` and file references in the README, notebook, and report.
