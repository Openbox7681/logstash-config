Elasticsearch to CSV
================

###Install Plugin
```sh
./bin/logstash-plugin install logstash-output-csv
```

### es2csv.config
```
input {
  elasticsearch {
    hosts => "127.0.0.1:9200"
    index => "log"
    query => '{"query":{"match_all":{}}}'
  }
}


output {
  stdout { codec => dots }
  csv {
      fields => [ 'name','email' ]
      path => 'log.csv'
  }
}
```

