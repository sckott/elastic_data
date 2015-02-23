elastic datasets
================

This is a collection of smallish datasets to use for playing with Elasticsearch. 

You can only fit so much data in an R package. The R client for Elasticsearch we're
making already has some data in it, but of course it's nice to have more, so here it
is. 

## Datasets

* `plos_everything.json`
* `plos_introductions.json`
* `plos_data.json`
* `geonames_elastic_bulk.zip` - too big for gitub, [at dropbox](https://www.dropbox.com/s/50ddvxmgikx5hze/geonames_elastic_bulk.zip?dl=0)
* `gbif_data.json`
* `gbif_geo.json`
* `gbif_geopoint.json`
* `gbif_geoshape.json`
* `gbif_geosmall.json`
* `shakespeare_data.json`

## Loading into ES

These datasets are formatted to be ready for bulk loading into Elasticsearch 
via the [bulk API](http://www.elasticsearch.org/guide/en/elasticsearch/reference/current/docs-bulk.html)

`geonames_elastic_bulk.zip` is about 70 `.json` files in Elasticsearch bulk format. It was prepared from the [Geonames](http://www.geonames.org/) database at [http://download.geonames.org/export/dump/](http://download.geonames.org/export/dump/). The original data from Geonames was licensed under a Creative Commons Attribution 3.0 License, see [http://creativecommons.org/licenses/by/3.0/](http://creativecommons.org/licenses/by/3.0/).

To load the geonames data into Elasticsearch, do as you wish, but e.g., in R you could do 

```r
devtools::install_github("ropensci/elastic")
library("elastic")
files <- list.files("path/to/unzipped/files")
for(i in seq_along(iter)){
  invisible(
    docs_bulk(
      sprintf("path/geonames%s.json", iter[i])
    )
  )
}
```

The `docs_bulk()` function uses the `/_bulk` endpoint to `POST` data to an index in your ES server.
