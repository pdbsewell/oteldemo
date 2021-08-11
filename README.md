# oteldemo

*IMPORTANT:* This is a pre-released version of the OpenTelemetry Collector.

This demo contains server applications that use the
opentelemetry Go library for instrumentation and for sending telemetry data
to the opentelemetry collector.

This demo presents the typical flow of observability data with multiple
OpenTelemetry Collectors deployed:

- The Icy client sends data directly to the OTel Collector;
- The OTel Collector then sends the data to the appropriate backend, in this demo
 Jaeger, Zipkin, and Prometheus;

This demo uses `docker-compose` and by default runs against the 
`otel/opentelemetry-collector-dev:latest` image. To run the demo, switch
to the `oteldemo` folder and run:

```shell
docker-compose up -d
```
The demo exposes the following frontends:
- OTel Collector at http://localhost:55681

The demo exposes the following backends:

- Jaeger at http://0.0.0.0:16686
- Zipkin at http://0.0.0.0:9411
- Prometheus at http://0.0.0.0:9090 

Notes:

- It may take some time for the application metrics to appear on the Prometheus
 dashboard;

To clean up any docker container from the demo run `docker-compose down` from 
the `oteldemo` folder.


