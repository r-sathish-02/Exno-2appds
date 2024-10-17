# EX-02 PERFORMING DATA COLLECTION THROUGH WEB SCRAPING
### Aim:
To Perform Data Collection through web scraping using python.

### Algorithm:
Step 1: Include the Necessary python libraries.<br>
Step 2: Use the requests library to send HTTP requests to a web page.<br>
Step 3: Retrieve the HTML content and use BeautifulSoup to parse it.<br>
Step 4: Navigate and extract the necessary data.<br>
Step 5: Handle the Java script content and retrieve the data using the html tags.<br>
Step 6: Check with the website permission and scrap the content.<br>

### Program:
##### Importing necessary libraries
```Python
import requests
from bs4 import BeautifulSoup
import pandas as pd
```
##### Fetching the webpage
```Python
url = 'https://www.w3schools.com/sql/sql_insert.asp'
response = requests.get(url)
response
```
##### Parsing HTML and extracting headings
```Python
soup = BeautifulSoup(response.content, 'html.parser')
headings = soup.find_all('h2')
headlist=[x.text for x in headings]
print(headlist)
```
##### Creating DataFrame and saving to CSV
```Python
df=pd.DataFrame(headlist,columns=['Headings'])
df.to_csv('newdata.csv', index=False)
df
```

### Output:

#### Response Code:

![image](https://github.com/user-attachments/assets/f703f18d-7992-424d-93f3-d14936131c5d)

#### Heading Code:

![image](https://github.com/user-attachments/assets/c6cf0b06-623a-4183-8117-66e4e47b5d19)

#### DataFrame:

![image](https://github.com/user-attachments/assets/f86aa3b6-8125-4fc9-a848-74f87c9ebb21)



### Result:
Thus , data Collection through web scraping using python is successfully performed.
