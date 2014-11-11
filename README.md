elastic datasets
================

This is a collection of smallish datasets to use for playing with Elasticsearch. 

You can only fit so much data in an R package. The R client for Elasticsearch we're
making already has some data in it, but of course it's nice to have more, so here it
is. 

## Datasets

* plos_everything.json
* plos_introductions.json

## Loading into ES


These datasets are formatted to be ready for bulk loading into Elasticsearch 
via the [bulk API](http://www.elasticsearch.org/guide/en/elasticsearch/reference/current/docs-bulk.html)
