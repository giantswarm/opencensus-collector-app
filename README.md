[![CircleCI](https://circleci.com/gh/giantswarm/opencensus-collector-app.svg?style=shield)](https://circleci.com/gh/giantswarm/opencensus-collector-app)

# opencensus-collector

This chart simply installs [opencensus collector](https://opencensus.io/service/components/collector/).
It allows to configure 4 different receivers and is pre-configured to export only to Jaeger.

## Configuration

| Option | Default | Decription |
|--------|---------|------------|
|jaegerURL|http://jaeger.tracing:14268/api/traces|URL of Jaeger server to output data with Jaeger exporter|
|enableOpencensusReceiver|true|enable opencensus protocol receiver (default port: 55678)|
|enableZipkinReceiver|true|enable zipkin protocol receiver (default port: 9411)|
|enableJaegerReceiver|true|enable jaeger protocol (both TChannel and HTTP) receiver (default ports: 14267 & 14268)|

## Requirements

- needs Jaeger to export the data, but will start even without Jaeger present

## Installation

The application doesn't need any dependencies nor config, so it's sufficient to run:

```text
helm install -n tracing giantswarm-playground-catalog/opencensus-collector-app
```

## Compatibility

Tested on Giant Swarm release 11.0.1 on AWS with Kubernetes 1.16.3
