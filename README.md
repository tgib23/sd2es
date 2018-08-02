# sd2es

Just a script to upload support dump to Elasticsearch.

## Requirement

* logstash
    * `$ curl -L -O https://artifacts.elastic.co/downloads/logstash/logstash-6.0.1.zip && unzip logstash-6.0.1.zip`
	* `$ sudo yum install logstash` 
	* etc.,

* jq
    * `$ brew install jq`
    * `$ sudo yum install -y jq`
	* etc.,

## How to Use

1. Set environment variables in `sd2es`.
```
# Should be fixed depending on your environment
LOGSTASH_COMMAND=/usr/share/logstash/bin/logstash
TIMEZONE="Asia/Tokyo"
```
2. Run `sd2es` requires three arguments, support-dump, index, and elasticsearch hosts.
```
$ bash sd2es mysupport-output-01.tar case_xxxxx "http://node0:9200,http://node1:9200,http://node2:9200"
```

