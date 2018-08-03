# sd2es

Just a script to upload support dump to Elasticsearch.

## Requirement

* logstash
    * `$ curl -L -O https://artifacts.elastic.co/downloads/logstash/logstash-6.0.1.zip && unzip logstash-6.0.1.zip`
    * `$ brew install logstash` 
    * `$ sudo yum install logstash` 
    * etc.,

* (Optional) jq
    * `$ brew install jq`
    * `$ sudo yum install -y jq`
    * etc.,

## How to Use

1. Set environment variables in `sd2es`.

TIMEZONE should be modified depending on the customer's location.
Use `Canonical ID` listed [here](http://joda-time.sourceforge.net/timezones.html).
```
# Should be fixed depending on your environment
LOGSTASH_COMMAND=/usr/share/logstash/bin/logstash
TIMEZONE="Asia/Tokyo"
```
2. Run `sd2es` requires three arguments, support-dump, index, and elasticsearch hosts.
```
$ bash sd2es mysupport-output-01.tar case_xxxxx "http://node0:9200,http://node1:9200,http://node2:9200"
```

Depending on your ES and client env, It will take some time to upload those files.
Recommend to upload before coffee/lunch break.

3. Go to Kibana -> Settings. Input the index name, use @timestamp as Time-field name, and click Create.

![kibana](https://raw.githubusercontent.com/tgib23/sd2es/master/kibana.png)
