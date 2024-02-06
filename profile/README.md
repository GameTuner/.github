# GameTuner Project

GameTuner is a data platform, specialized in mobile gaming, built on top of Snowplow Open Source data pipeline. It comes with preset BI tool and integrations. We focused on satisfying the whole business vertical needs in Mobile Gaming.

## What GameTuner solves

Game Tuner is specialized for mobile game development. Below are some of the areas that GameTuner solves:
- It handles offline data and data latency. 
- Unique ID for multi-device users. This is something that GameTuner solve out of the box.
- Due to the unstable internet connection some devices don’t get ok response from server and try to send already sent data. It handles duplicated data sent from device.
- It calculates event loss percentage and report that to analytics users. Event loss is calculated based on event index tracked on user device.
- Does data modelling specific for gaming. 
- Provideds direct access to both telemetry data and modelled data. 
- It contains a query engine that implements semantic layer between modeled data and end user with 150+ out of box metrics.
- A metadata service that holds and handle all meta information about registered games and system.
- It supports separate datasets for every registered application (games).
- It handles currency conversion for in app purchases.
- Everything is built on top of GCP.

## GameTuner Components

GameTuner is built on top of Snowplow Open Source data pipeline. It contains next components:

- [GameTuner Unity SDK][gametuner-unity-sdk] - a Unity SDK that collects events from mobile games and sends them to the pipeline.
- [GameTuner Collector][gametuner-collector] - a collector application that collects events from tracker and sends them to the pipeline.
- [GameTuner Enricher][gametuner-enricher] - an enricher application that enriches events with additional data and sends them to the pipeline.
- [GameTuner Loader][gametuner-loader] - a loader application that loads enriched events into BigQuery.
- [GameTuner Query Engine][gametuner-query-engine] - a query engine that implements semantic layer between modeled data and end user with 150+ out of box metrics.
- [GameTuner Metadata Service][gametuner-metadata-service] - a metadata service that holds and handle all meta information about registered games and system. One part of the service deals with schema maintenance.
- [GameTuner ETL Service][gametuner-etl-service] - an ETL service that does data modelling specific for gaming. Developed in AirFlow and deployed on GCP Composer. 
- [GameTuner Enrich Bad Sink][gametuner-enrich-bad-sink] - a service that is responsible for sinking pub/sub messages from enrich bad topic to BigQuery.

Below is the architecture of GameTuner solution:

![GameTuner Architecture](../docs/images/gametuner-architecture.png)

[gametuner-unity-sdk]:https://github.com/GameTuner/unity-tracker.git
[gametuner-collector]:https://github.com/GameTuner/collector.git
[gametuner-enricher]:https://github.com/GameTuner/enricher.git
[gametuner-loader]:https://github.com/GameTuner/bigquery-loader.git
[gametuner-query-engine]:https://github.com/GameTuner/query-engine.git
[gametuner-metadata-service]:https://github.com/GameTuner/metadata.git
[gametuner-etl-service]:https://github.com/GameTuner/etl.git
[gametuner-enrich-bad-sink]:https://github.com/GameTuner/enrich-bad-sink.git
