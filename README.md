# Elasticsearch Ingest pipeline examples

_Pipelines pre-process documents before indexing, the Ingest node type in Elasticsearch includes a subset of Logstash functionality, part of that are the Ingest pipelines. All Elasticserach nodes enable ingest by default, this is configurable._

If you have used Logstash you'll recognize the different [processors](https://www.elastic.co/guide/en/elasticsearch/reference/6.4/ingest-processors.html) you can use to transform data before the document(s) are indexed. 

The Ingest pipelines comes with a simulation API that can be used to test pipelines, it's easy to add a couple of example documents to dry-run them through a pipeline. 

Besides testing the pipelines with the simulation API it's easy to handle errors within a pipeline, e.g. if an processor fails for some reason you can use the `on_failure` block to change the index to something like `failed-my-index`. You can also use `ignore_failure` to ignore an error and move on to the next processor.

All of the examples in this repository can easily be translated and used with the Dev Tool in Kibana.

## Run Elasticsearch and Kibana in Docker

To run the examples in this repository as-is:

1. Run the `run_elastic.sh` script
```
bash run_elastic.sh
```
2. You should now be able to reach Elasticsearch on `http://localhost:9200` and Kibana on `http://localhost:5601`

## Notes

* Tested on Elasticsearch and Kibana version `6.4`

## Examples

* [Simple pipeline example](https://github.com/mikejoh/elastic-ingest-pipeline-examples/blob/master/examples/simple-pipeline/) (uses the [`remove`](https://www.elastic.co/guide/en/elasticsearch/reference/6.4/remove-processor.html) processor)
* Handling errors in a pipeline
* Using the simulation API
* Advanced pipeline example (uses a combination of processors)