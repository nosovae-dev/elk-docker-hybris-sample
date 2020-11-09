# Elastic stack (ELK) + Filebeat for Monitoring Hybris logs on Docker

This is extended version from [Elastic stack (ELK) + Filebeat for Monitoring Nginx on Docker](https://github.com/GeminiWind/docker-elk-nginx-filebeat). Filebeat takes in charge of streaming log file from nginx to Logstash then processing it and visualize to Kibana.

## What 's insides 

```
.
├── LICENSE
├── README.md
├── docker-compose.yml
├── elasticsearch
│   ├── Dockerfile
│   └── config
│       └── elasticsearch.yml
├── elk-docker-hybris-sample.iml
├── filebeat
│   ├── Dockerfile
│   └── config
│       └── filebeat.yml
├── kibana
│   ├── Dockerfile
│   └── config
│       └── kibana.yml
├── logs
└── logstash
    ├── Dockerfile
    ├── config
    │   └── logstash.yml
    └── pipeline
        └── hybris.conf
```

- Logs: folder with Hybris logs
- Elasticsearch: containing build image and configure for Elasticsearch
- Filebeat: containing build image and configure for Filebeat to streaming log of Nginx to Logstash
- Logstash: containing build image and configure pipeline for Logstash to process sent log file from Filebeat
- Kibana: containing build image and configure for Kibana to visualize data

## Getting Started

To run this stack, run the following command
```bash
docker-compose up
```
Then go to `http://localhost:5601` to see your data in Kibana

Default Kibana user information
- Username: elastic
- Password: changeme
