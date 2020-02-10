---
layout: page
title: Implementations
---

This page gives a quick overview of the history of the GEO Label implementations, tools, and the developments after the GeoViQua project.
The GeoViQua team consciously decided to develop two implementations of the GEO Label API to increase the potential for reusability by third parties.

## Architecture and common files

At the core of the implementation lies the mapping of geospatial metadata fields to specific facets of the label.
Since the originating metadata documents are based on XML representations, the fields are identified by XPath queries.
To maintain only a single point of change for the live services during the GeoViQua, the implementations accessed publicly available mapping files from a central repository at [https://geoviqua.github.io/geolabel/](https://geoviqua.github.io/geolabel/) ([GitHub repo](https://github.com/GeoViQua/geolabel)).

This allowed to update the sources for label information without redeploying the service instances.
For backup, each implementation had a copy of the most recent mapping configurations at the time of deployment.
Note that this central repository is _not_ up to date with extensions described below.

## Java implementation

Developed by 52°North as part of the GeoViQua project: [https://github.com/GeoViQua/GEO-label-java](https://github.com/GeoViQua/GEO-label-java)

**License**: The Apache License, version 2.0

This project had some continued developments as part of small, independent research projects, extending the GEO Laben for use cases in the [Sensor Web](https://en.wikipedia.org/wiki/Sensor_Web) domains.
These extensions are maintained in different forks:

- Sensor Web metadata using [OGC Sensor Web Enablement](https://www.opengeospatial.org/projects/groups/sensorwebdwg) suite of standards, see [References](/references) for a scientific paper with more information: [https://github.com/52North/GEO-label-java](https://github.com/52North/GEO-label-java)
- Semantic Sensor Web metadata based on [SSNO](https://www.w3.org/TR/vocab-ssn/), [References](/references) for a scientific paper with more information; this fork also maintains a Docker image and demonstrates the deployment of the GEO Label API into [serverless infrastructures](https://en.wikipedia.org/wiki/Serverless_computing), such as Google Cloud Run and AWS Lambda: [https://github.com/nuest/GEO-label-java/](https://github.com/nuest/GEO-label-java/)

## PHP implementation - discontinued

[https://github.com/GeoViQua/geolabel-service](https://github.com/GeoViQua/geolabel-service)

PHP Framework: Symfony

**License**: The Apache License, version 2.0
