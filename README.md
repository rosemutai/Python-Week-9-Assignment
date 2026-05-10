# Python-Week-9-Assignment

This project demonstrates how to work with JSON data and APIs using Python, focusing on Working with JSON Data from GitHub and Working with DummyJSON API Endpoints.
It covers:
- Creating and handling JSON data
- Extracting data from GitHub raw files
- Consuming REST APIs endpoints
- Transforming data into DataFrames
- Exporting datasets as CSV files

## Working with JSON Data from GitHub
1. To get data, I used Mockroo to genarate the airbnb dataset then exported this dataset as `.json` file
2. Upload this data to GitHub
3. Retrieve the raw GitHub URL
4. Extract JSON Data using Python
   ```python
import requests
import pandas

url = 'https://raw.githubusercontent.com/rosemutai/Airbnb-Dataset-in-Kenya/refs/heads/main/airbnb.json'

# Request data
data_content = requests.get(url)
json_data = data_content.json()

# Convert to DataFrame
data_df = pandas.DataFrame(json_data)

# Save to CSV
data_df.to_csv('kenyan_airbnb.csv')

## Working with DummyJSON API
I extracted data from two endpoints:
`https://dummyjson.com/products `
`https://dummyjson.com/carts `

### Products
```
import requests
import pandas

products_url = 'https://dummyjson.com/products'

# Request data
products_data = requests.get(products_url)
json_products = products_data.json()

# Get the products content
products = json_products['products']

# Convert to DataFrame
products_df = pandas.DataFrame(products)

# Save to CSV
products_df.to_csv('products.csv')
```
### Carts

```
import requests
import pandas

carts_url = 'https://dummyjson.com/carts'

# Request data
data_res = requests.get(carts_url)
data_json = data_res.json()

# Get the carts content
data = data_json['carts']
# Convert to DataFrame
data_df = pandas.DataFrame(data)

# Save to CSV
data_df.to_csv('carts.csv')
```
## Skills
- JSON Parsing & Transformation
- Working with `Pandas` Library to transform Data and export Data  as cSV format

  ## Techstack
  - Python
  - Pandas
  - Requests

