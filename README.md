# UCBerkleyHackathon

• Project name: Social Justice During the COVID-19 


• Description: During the pandemic, we all concern about public health safety, but social justice is crucial and should not be forgotten. From the past up until now people in the United States have been treated unequally. With these two situations, this project prepares the data from Tweeter social media using hashtag and the location to trace where the demonstration occurs as well as the data from Kaggle website to check which location has high corona virus cases. You can make the application buy using these datasets
	
•	Installation: No need to install, what you need to do is to apply for a developer account in Tweeter (https://developer.twitter.com/en/docs...)  if you want you can install a JupiterLab in your local computer but you can also run it online.  https://hub.gke.mybinder.org/user/jupyterlab-jupyterlab-demo-2d0hqm4r/lab  


•	Usage: Importing all necessarily libraries

```ruby
	import http.client 
	import mimetypes
	import json
	import matplotlib.pyplot as plt
	import numpy as np
	from wordcloud import WordCloud, STOPWORDS 
	import matplotlib.pyplot as plt 
	import pandas as pd 
	import mimetypes

```

Request HTTP to connect the tweeter’s API and get the response data as a JSON file (you can choose the type of the file you want API to repose to you). Replace #add bearer key to your barer token and # add personalization to you personalization id


```ruby
conn = http.client.HTTPSConnection("api.twitter.com")
payload = ''
headers = {
  'Authorization': 'Bearer', #add bearer key
  'Cookie': 'personalization_id="'# add personalization
}
conn.request("GET", "/1.1/search/tweets.json?q=BlackLivesMatter%20since:2020-05-20&lang=en&%23protestl&result_type=recent", payload, headers)
res = conn.getresponse()
data = res.read()
#print(data.decode("utf-8"))

unstructured_tweets = json.loads(data)
indent_tweets = json.dumps(json.loads(data), indent=2)
#print(indent_tweets)
#print(unstructured_tweets)
data = json.loads(indent_tweets)

with open('tweets.json', 'w') as f:
    json.dump(data, f, indent=4)

text = ''
with open("game.txt", "w", encoding='utf-8') as text_file:
    for status in data['statuses']:
        text += status['text']
        text += ' '
        print(status['text'])
        text_file.write(status['text'])


```


Sample output from code above

```ruby

```
