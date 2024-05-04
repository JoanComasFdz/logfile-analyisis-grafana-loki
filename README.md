# logfile-analyisis-grafana-loki
Contains a Promtail - Grafana Loki - Grafana stack to analyze existing log files from a local drive.

## Run

1. Set the path of the directory containing the logs you want to analyze in the [.env](.env) file.

2. `docker-compose up -d`
3. Open:http://localhost:3000/ (admin:admin)
4. Open Dashboard "All log lines".

Now you can start exploring your logs with [LogQL](https://grafana.com/docs/loki/latest/logql/).

## Management

### Promtail
- http://localhost:9080

### Loki
- http://localhost:3100/ready
- http://localhost:3100/metrics

Use the file [api.http](api.http) to test the Loki API.

## How it works
1. Promtail reads .log files.
2. Then sends them to Loki.
3. Loki stores the logs.
4. Grafana queries them using LogQL.