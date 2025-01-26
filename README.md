# List_of_largest_companies_in_the_United_States_byrevenue in 2024

## Project Overview: - Objectives and goals of the scraping project. 

Extracting data from the web can often feel overwhelming, with web scraping, we are able to automate structured data retrieval from websites, facilitating the collection, analysis and genration of insights that are not readily available.

The goal of this project is to extract data from the wikipedia website by inspecting the websites html elements and attributes, converting the dataframe to a csv file, for further analysis.

## Tools and Libraries:

- JupyterNotebook: environment for writing and running .

- Requests: for making HTTP requests to retrieve web pages.

- BeautifulSoup4: for parsing and navigating HTML content.

- Pandas: For organizing and analyzing the extracted data.

## Target Website Information: (URL)[https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue]

## Data Extraction Logic: 

- Fetching the Web Page:
The script uses requests.get() to fetch the HTML content of a Wikipedia page.

 -Parsing HTML:
BeautifulSoup parses the HTML to identify key elements such as tables, headings, and paragraphs.

- Extracting Data:
Specific data, like tables, are extracted using tags and classes (e.g., <table>).

- Cleaning and Structuring Data:
The extracted data is cleaned, transformed into a structured format, and saved into a DataFrame for easy analysis.

Codebase: - Include the actual code with clear comments. - Explain key functions, variables, and decision points.
