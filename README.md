# sd2es

Just a script to upload support dump to Elasticsearch.

## Requirement

* logstash
    * `$ brew install logstash`
	* `$ sudo yum install logstash` 

* jq
    * `# yum install -y jq`

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

