# Level1

google sheet `Parser_ImageSize: `
'https://docs.google.com/spreadsheets/d/1GK9xSBOP1iWq0D8CeXV8WT4zJ-IeVP0IRQokLi0xbTE/edit#gid=1902149593'

for writing data to google sheet you need add your google api key with name `keys.json`, example in file `keys.json.sample`


# Level2

google sheet `BigQuery: `
'https://docs.google.com/spreadsheets/d/1eDftTF9aBOBE2dkV3o6Wies3IASts-AXqKkQw78nNuc/edit#gid=491402103'

for writing data to google sheet you need add your google api key with name `keys.json`, example in file `keys.json.sample`
for getting data from BigQuery you need add your google api key with name `level2_key.json`, example in file `level2_key.sample`

Competitive pipeline was built using a combination of Python packages to efficiently analyze and process data,
interact with Google BigQuery, and store results in Google Sheets.
The key Python packages utilized in this pipeline include:

1. concurrent.futures: Used for concurrency the fetching of data
from BigQuery by employing ThreadPoolExecutor to improve performance.
2. concurrent.futures.ThreadPoolExecutor: Employed
to concurrently write multiple dataframes to different Google Sheets worksheets, improving the efficiency of the process
3. google.cloud.bigquery: Employed for interacting with Google BigQuery to execute SQL queries and retrieve data.
4. pandas: Played a central role in data manipulation and analysis, enabling
the aggregation, grouping, and transformation of data for various analytics tasks.
5. gspread: Utilized for interacting with Google Sheets, facilitating
the writing of analyzed dataframes to separate worksheets
6. oauth2client.service_account: Used for authenticating
and authorizing access to Google Sheets via Service Account Credentials

Concurrency retrieving data from BigQuery took 1.86 seconds in my virtual
environment, and concurrency writing to a Google Spreadsheet took 4.8 seconds


# Level3

google sheet `Parse_estates: `
'https://docs.google.com/spreadsheets/d/1tfRaOMN-O208IuUNaKSkWm3JHh335OYyMAEULXlX_CM/'

I got ingo from first 50 links to estate for saving time,
but I use all links to write to sheetwhat I got with BeautifulSoup

I implemented BeautifulSoap using query because it can be faster than selenium, but there is one drawback, 
the detail page doesn't show the locale, so I took it from the list page ith links.

In this task I parsed site `https://www.olx.ua/uk/nedvizhimost/` where I got info:
1. title from the announcement as string
2. price to estate as string, because there could be грн, $ or something else
3. floor where is estate as integer
4. storey - how march floors in the building as integer
5. locality - where the estate is located as string
6. area - how many square meters are in estate
