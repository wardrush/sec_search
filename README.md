# sec_search
---

# Edgar Filings Parser

This Jupyter Notebook provides a toolset for extracting and analyzing financial reports (specifically 10-K filings) from the SEC's EDGAR database. The project is tailored for individuals interested in financial data analysis, offering integration with the SEC EDGAR website to fetch the most recent 10-K filings of publicly traded companies.

## Features

- **Automated Retrieval of 10-K Filings:** Automates the process of retrieving the most recent 10-K filings from the SEC EDGAR database.
- **CIK Lookup:** Includes functionality to read tickers from a `tickers.txt` file to create a CIK lookup table, allowing for easy access to company filings using stock ticker symbols.
- **Parsing and Analysis:** Offers tools to parse the raw 10-K filings and extract specific sections, such as the "Item 1A. Risk Factors" section, using regular expressions.
- **Threaded Requests:** Utilizes threaded calls to manage API requests efficiently, staying under the SEC's rate limit for data retrieval.

## How It Works

1. **Initialization:** The notebook begins by importing necessary libraries such as `pandas`, `requests`, and `re` for data manipulation, web requests, and regex operations, respectively.

2. **Workflow Overview:**
   - The workflow starts with reading a `tickers.txt` file into a Python variable for CIK lookup.
   - The `PublicCompany` class correlates a given ticker with its CIK and fetches the most recent 10-K filing.
   - The `FilingRequester` class manages the headers and URL assembly for SEC EDGAR requests.
   - The `PublicFiling` class creates a parsed version from the raw filing, focusing on extracting the "Item 1A" section.
   - The `SECDataManager` class orchestrates threaded calls for various tickers, aggregation, and output of those calls.

3. **Usage Example:**
   The notebook includes an example of how to create an instance of the `PublicCompany` class using the ticker 'UNH' (for UnitedHealth Group Incorporated) to fetch and parse the most recent 10-K filing.

## Getting Started

To use this notebook:

1. Ensure you have JupyterLab or Jupyter Notebook installed.
2. Clone this repository to your local machine.
3. Open `Edgarv07.ipynb` in JupyterLab/Notebook.
4. Follow the instructions within the notebook to install any required dependencies.
5. Run the cells in order to execute the parsing script.

## Contributing

Your contributions are welcome! Please feel free to submit pull requests with improvements, bug fixes, or enhancements.

## License

This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT).
