# Scraping-Guardian
Using Guardian API, we scrape news data about Bangladesh

# Guardian API

The Guardian API is a public web service that provides access to all of the content that the Guardian creates, including articles, images, audio, and videos dating back to 1999. The API is open to anyone, and it can be used to build a wide variety of applications, such as news aggregators, social media bots, and educational tools.

To access the Guardian API, you need to create an account and obtain an API key. Once you have an API key, you can start making requests to the API. The API supports a variety of different endpoints, which allow you to retrieve content based on different criteria, such as topic, date, or section.

For example, you could use the Guardian API to retrieve a list of all of the articles that have been published in the past hour about the war in Ukraine. Or, you could use the API to retrieve the full text of a specific article.

The Guardian API also supports a variety of different query parameters, which allow you to refine your requests. For example, you could specify the language of the content that you want to retrieve, or the number of results that you want to return.

The Guardian API is a valuable resource for anyone who wants to access and use the Guardian's content. It is easy to use, and it provides a wide range of features and functionality.

[API Documentataion](https://open-platform.theguardian.com/documentation/)

# Getting News Data

We decided to get news titles from 2010 to 2023. The API we're using is **https://content.guardianapis.com/world/bangladesh?from-date={start_date}&api-key={API_KEY}&type=article&page=x**

The API Results are returned as a paginated list, with a default of 10 results. In order to page through the results, you can add the *page* keyword to your query. So, at first we learn the total number of pages by the *pages* key from the json response. Using this page number limit, we create the api urls.

Then we call these api urls using the *requests* library to receive the 10 news article search results for each of the page api url. The results are stored in a list that is further processed to get the news title, category, date, and news-url for each of the news article. These information are saved in a dataframe. 

The code: [guardian_news_scraper.ipynb]()

The saved data: 

# Reference

