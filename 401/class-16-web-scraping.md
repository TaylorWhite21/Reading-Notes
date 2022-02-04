# Web Scraping

Web scraping is used to automatically access and extract large amounts of information from a website.
It is ideal to read the robot.txt file for a website and follow the rules for web scraping the site. 
You can find the robot.txt file on websites. It is usually the root directory of a website – http://example.com/robots.txt.

If a site does not want to be scraped, it will contain lines like:
User-agent: *
Disallow:/

A few giveaways that let an anti-scrape tool know you are scraping are:
- Scraping too fast and too many pages, faster than a human ever can.

- Following the same pattern while crawling. For example – go through all pages of search results, and go to each result only after grabbing links to them. No human ever does that.
- Too many requests from the same IP address in a very short time
- Not identifying as a popular browser. You can do this by specifying a ‘User-Agent’.
- Using a user agent string of a very old browser

You can find steps to take to avoid anti-scrape tools by reading [this article](https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/)
<br>
<br>

## How to Web scrape:
1. On the website, right click and select "inspect".
2. In the top left of the inspect window, there is and arrow symbol, select it. This arrow is used to select an area of the webpage and the code for that will be highlighted in the console.
3. Import thr following libraries to your editor
```
import requests
import urllib.request
import time
from bs4 import BeautifulSoup
```
4. Create a URL variable and assign the url of the webiste to it make a request to it. If it was successful, you will get a 200 response.
```
url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)
```

5. Parse the HTML with [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/).
```
soup = BeautifulSoup(response.text, “html.parser”)
```
6. Use the findAll method to locate the <a> tags.
This will give us every line of code that has an <a> tag.
```
soup.findAll('a')
```
7. Extract the link that you want. For this example, the link we want is on line 38.
```
one_a_tag = soup.findAll(‘a’)[38]
link = one_a_tag[‘href’]
```
8. This code saves the first text file, ‘data/nyct/turnstile/turnstile_180922.txt’ to our variable link. The full url to download the data is actually ‘http://web.mta.info/developers/data/nyct/turnstile/turnstile_180922.txt’. Use the urllib.request library to download this file path to our computer. We provide request.urlretrieve with two parameters: file url and the filename.
```
download_url = 'http://web.mta.info/developers/'+ link
urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:])
```
9. Be sure to add the below code, so that the website is not being spammed by your request.
```
time.sleep(1)
```
10. Below is code to web scrape a website using a for loop.
```
# Import libraries
import requests
import urllib.request
import time
from bs4 import BeautifulSoup

# Set the URL you want to webscrape from
url = 'http://web.mta.info/developers/turnstile.html'

# Connect to the URL
response = requests.get(url)

# Parse HTML and save to BeautifulSoup object¶
soup = BeautifulSoup(response.text, "html.parser")

# To download the whole data set, let's do a for loop through all a tags
line_count = 1 #variable to track what line you are on
for one_a_tag in soup.findAll('a'):  #'a' tags are for links
    if line_count >= 36: #code for text files starts at line 36
        link = one_a_tag['href']
        download_url = 'http://web.mta.info/developers/'+ link
        urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:]) 
        time.sleep(1) #pause the code for a sec
    #add 1 for next line
    line_count +=1
```
