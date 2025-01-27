# List of largest companies in the United States by revenue in 2024

## Project Overview: - Objectives and goals of the scraping project. 

Extracting data from the web can often feel overwhelming, with web scraping, we are able to automate structured data retrieval from websites, facilitating the collection, analysis and generation of insights that are not readily available.

The goal of this project is to extract data from the wikipedia website by inspecting the websites html elements and attributes, converting the dataframe to a csv file, for further analysis.

## Tools and Libraries:

- JupyterNotebook: this environment was used for writing and running codes.

- Requests: for making HTTP requests to retrieve web pages.

- BeautifulSoup4: for parsing and navigating HTML content.

- Pandas: For organizing and analyzing the extracted data.

## Target Website Information: [URL](https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue)

## Data Extraction Logic: 

- Fetching the Web Page:
The script uses requests.get() to fetch the HTML content of a Wikipedia page.

 - Parsing HTML:
BeautifulSoup parses the HTML to identify key elements such as tables, headings, and paragraphs.

- Extracting Data:
Specific data, like tables, are extracted using tags and classes.

- Cleaning and Structuring Data:
The extracted data is cleaned, transformed into a structured format, and saved into a DataFrame for easy analysis.

- Export Data to CSV

## Code:
```
# first, import BeautifulSoup and requests

from bs4 import BeautifulSoup
import requests
```

```
# Specify URL and fetch the HTML content of the page

url = 'https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue'

page = requests.get(url)

# Parse the HTML content
soup = BeautifulSoup(page.text, 'html')
```
```
# View structure of the HTML

print(soup)
```
```
# Table one is needed; therefore:

table = soup.find('table')
print(table)
```
```
# Extract header row
headings = table.find_all('th')
headings

# let's turn the returned headings to a list and call it 'table title'

table_titles = [title.text.strip() for title in headings]
print(table_titles)

# Creating a dataframe using pandas

import pandas as pd
df = pd.DataFrame(columns =table_titles) 
df

# find rows in the web table for each column 
column_data = table.find_all('tr')

# Inserting individual data into rows and then into the pd dataframe

for row in column_data[1:]:
    row_data = row.find_all('td')
    individual_row_data = [data.text.strip() for data in row_data]
    
    # print(individual_row_data )  
    length = len(df)
    df.loc[length] = individual_row_data 
df
```
```
# Convert dataframe to csv file

df.to_csv(r'C:\Users\IVANN\Python Web Scraping Outputs\Companies.csv', index = False)
```
