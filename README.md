# -Web-Scraping-using-Python-selenium
#It is a internship assignment
from selenium import webdriver
import pandas as pd

# Initialize the Chrome webdriver
driver = webdriver.Chrome()

# Open the webpage to scrape
url = "URL_OF_THE_WEBPAGE_TO_SCRAPE"
driver.get(url)

# Extract relevant information (example: text, images, links)
# Replace these lines with your scraping logic
data = []
elements = driver.find_elements_by_xpath("//div[@class='example']")
for element in elements:
    text = element.text
    data.append(text)

# Close the webdriver
driver.quit()

# Store the scraped data in a structured format (in this case, Excel)
df = pd.DataFrame(data, columns=["Scraped Data"])
df.to_excel("scraped_data.xlsx", index=False)

print("Data scraped and saved to scraped_data.xlsx")
