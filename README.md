# Elasticsearch-and-python
We often face service breakdowns and we can just see the overview of it in Grafana or Kibana in the form of time series but what if we want to dig deep and there is a need of root cause analysis. As our elastic cluster hold data for just the past two weeks so its very important that we should get the data of the breakdowns to analyze it and store it for future prospects. In this process I am going to describe certain ways to dump elastic cluster data into python in the form of data frame. Once we will get the raw data we can do any kind of analysis with it and can avoid same kind of interruption in future.

Getting started with Elasticsearch in python.

while working on Elasticsearch and python for the past few weeks. I had a hard time in figuring out how to get the raw data from the elastic cluster and dump it into pandas. In this process, I am going to describe certain ways to dump elastic cluster data into python in the form of the data frame. Once we will get the raw data we can do any kind of analysis which is limited in kibana.

Time to download the data will vary and will depend on the interval for which we are downloading the raw data. As we are getting a huge number of hits so it’s very important that we should filter our query and only download the data which is important for our analysis. We can put date and time filter to download the data. As in my case, my index name is date wise so I don’t have to worry about the date as one index is having one day of data. So, we can just put the time filter and parse the data.

I have different ways of downloading the data depending on the need so I will explain all the ways and one can use whatever is needed as per the situation.

1.) The first and most important step is to import all the libraries.

import pandas as pd
import datetime
import elasticsearch
import elasticsearch.helpers
from elasticsearch import Elasticsearch
from elasticsearch_dsl import Search
from pandasticsearch import DataFrame
from pandasticsearch import Select
from elasticsearch import Elasticsearch, helpers


