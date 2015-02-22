elastic datasets
================

This is a collection of smallish datasets to use for playing with Elasticsearch. 

You can only fit so much data in an R package. The R client for Elasticsearch we're
making already has some data in it, but of course it's nice to have more, so here it
is. 

## Datasets

* `plos_everything.json`
* `plos_introductions.json`
* `geonames_elastic_bulk.zip`

## Loading into ES

These datasets are formatted to be ready for bulk loading into Elasticsearch 
via the [bulk API](http://www.elasticsearch.org/guide/en/elasticsearch/reference/current/docs-bulk.html)

`geonames_elastic_bulk.zip` is about 70 `.json` files in Elasticsearch bulk format. It was prepared from the [Geonames](http://www.geonames.org/) database at [http://download.geonames.org/export/dump/](http://download.geonames.org/export/dump/). The original data from Geonames was licensed under a Creative Commons Attribution 3.0 License, see [http://creativecommons.org/licenses/by/3.0/](http://creativecommons.org/licenses/by/3.0/).
