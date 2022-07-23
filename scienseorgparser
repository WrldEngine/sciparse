import requests
from bs4 import BeautifulSoup
import time 

org = "https://www.science.org"
URL = 'https://www.science.org/topic/category/scientific-community'

start = time.time()
response = requests.get(URL)

soup = BeautifulSoup(response.content, 'html.parser')
publications = soup.find_all('div', class_='card pb-4 mb-4 border-bottom'); list_of_contents = []

for publication in publications:
    list_of_contents.append({
        'name'    : publication.find('a', class_='text-reset animation-underline').get('title'),
        'link'    : publication.find('a', class_='text-reset animation-underline').get('href'),
    })
for list_of_content in list_of_contents:
    print(f"Name: {list_of_content['name']}\nLink: {org}{list_of_content['link']}\n")
print(f"Time: {round(time.time() - start)} seconds")
