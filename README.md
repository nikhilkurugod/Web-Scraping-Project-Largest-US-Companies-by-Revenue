# Web-Scraping-Project-Largest-US-Companies-by-Revenue

1. Import Libraries: Imports BeautifulSoup for parsing HTML, requests for fetching web pages, and pandas for creating and manipulating dataframes.

2. Fetch Webpage: Retrieves the HTML content of the specified Wikipedia URL using requests.get().

3. Parse HTML: Uses BeautifulSoup to parse the HTML content, making it easy to navigate and extract data.

4. Locate Table: Finds all <table> elements in the parsed HTML.  It then assumes the desired table (containing the company data) is the first table found (index 0).  Important: Wikipedia's structure can change.  This hardcoded index might break if the page layout is updated.  A more robust approach would be to identify the table based on its attributes (e.g., class or id).

5. Extract Headers: Extracts the table headers (column names) from the <th> (table header) elements within the table.

6. Extract Data Rows: Iterates through each row (<tr>) in the table (skipping the header row). For each row, it extracts the cell values (<td>) and stores them in a list. This list is then appended to the data list, creating a list of lists.

7. Create DataFrame: Uses the pandas library to create a DataFrame from the extracted data. The previously extracted headers are used as column names.

8. Save to CSV: Saves the DataFrame to a CSV file named Companies_web_scrapped.csv in the specified directory. The index=False argument prevents the DataFrame index from being written to the file.

9. url : 'https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue'
