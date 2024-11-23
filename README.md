Saya hanya membuat simple scaping data berdasarkan hands on kemarin, di sini saya coba ambil data dari 'https://www.inews.id/multimedia/infografis'
1. url = 'https://www.inews.id/multimedia/infografis'
2. response = requests.get(url)
3. soup = BeautifulSoup(response.text, 'html.parser')
4. list_content = soup.select ('article')
5. list_content
6. len(list_content)
7. results = []
   for item in list_content:
   data = dict()

   data['title'] = item.select_one('.cardTitle').text
   data['url'] = item.select_one('.cardArticle a').get('href')
   data['url image'] = item.select_one('.thumbCard').get('src')
   results.append(data)
8. pd.DataFrame(results)
