# MQTT To Apache IoTDB

Ingesting time series data into Apache IoTDB using MQTT and EMQX | MQTT Apache IoTDB Integration

## Introduction

This tutorial will show you how to use MQTT to ingest time series data into Apache IoTDB. We will be using the [EMQX](https://www.emqx.io/) MQTT broker to publish and subscribe to messages. We will also be using the [Apache IoTDB](https://iotdb.apache.org) database to store the data.

EMQX with Apache IoTDB is another IoT time-series data integration solution:

- Data Storage and Processing: IoTDB is a high-performance time-series database that efficiently manages large-scale time-series data when integrated with EMQX.

- Data Analysis and Queries: IoTDB's SQL support allows real-time data transmission from EMQX and enables complex queries and analysis of historical data.

- Visualization and Monitoring: By integrating with tools like Grafana, real-time monitoring and visualization of data from IoTDB and EMQX create a unified monitoring platform.

## Architecture

| Name      | Version | Description                                                                      |
| --------- | ------- | -------------------------------------------------------------------------------- |
| [EMQX Enterprise](https://www.emqx.com/en/products/emqx)      | 5.1.1+  | MQTT broker used for message exchange between MQTT clients and the Apache IoTDB. |
| [MQTTX CLI](https://mqttx.app/cli) | 1.9.3+  | Command-line tool used to generate simulated data for testing.        |
| [Apache IoTDB](https://iotdb.apache.org)     | 1.1.2  | IIoT data storage and management.      |

## How to use

1. Please make sure you have installed the [docker](https://www.docker.com/), and then running the following commands to start the demo:

  ```bash
  docker-compose up -d
  ```

2. Use the following command to view time-series data through the IoTDB CLI

  ```bash
  # Enter the IoTDB container
  docker exec -it iotdb start-cli.sh

  # View the timeseries
  show timeseries;

  # View the data
  select * from root.iem.emqx_iem_simulate_1 limit 10;
  ```

## License

[Apache License 2.0](./LICENSE)
