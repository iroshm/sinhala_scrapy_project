# sinhala_scrapy_project
Web scraper made using python scrapy.

## Setup

support - https://docs.scrapy.org/en/latest/topics/settings.html

1. Install python 3
2. Install pip version 3
3. Install requirements by running this command,  pip install -r requirements.txt
4. Setup below configurations in the scrapy_IR/settings.py file as required.

### Configure a delay for requests for the same website (default: 0)
DOWNLOAD_DELAY = 9

### The download delay setting will honor only one of:
CONCURRENT_REQUESTS_PER_DOMAIN = 2
CONCURRENT_REQUESTS_PER_IP = 1

### Disable cookies (enabled by default)
COOKIES_ENABLED = False

5. To send data directly to ElasticSeach use following settings

### Configure ScrapeElasticSearch
ITEM_PIPELINES = {
    'scrapyelasticsearch.scrapyelasticsearch.ElasticSearchPipeline': 500
}

ELASTICSEARCH_SERVERS = ['http://127.0.0.1:9200']
ELASTICSEARCH_INDEX = 'sinhala_songs'              # index name
ELASTICSEARCH_TYPE = 'items'
ELASTICSEARCH_UNIQ_KEY = 'url'

6. Modify the starts_urls range according to your need .file path -  scrapy_IR/spiders/lyric_scrape_new.py 
  ( Recommand - Always keep page range as 1 page)

## Run


