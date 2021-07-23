---
layout: page
title: Home
---

<img title="GeoViQua logo" src="{{ 'assets/geoviqua_logo.png' | relative_url }}" style="float: right" width="150" />

The GEO Label is a metadata label to improve understandability of standardised geospatial metadata using a visual summary.
It was developed in the FP7 project [**GeoViQua**](https://www.creaf.uab.cat/projectes/geoviqua/).
Find out more on the official GEO Label website: [http://www.geolabel.info/](http://www.geolabel.info/home.htm).

This website presents the GEO Label Services, i.e., [implementations](/implementations) of a [RESTful API](/api) that allows generating GEO label in SVG, JSON, and PNG representations from supplied metadata records.
Find out more about the label and the [existing implementations](/implementations) and how they were extended, and take a look at the [references](#references) for more detailed information.

This website is maintained by [Daniel Nüst](https://nordholmen.net).

## GEO Label Examples

### Google Cloud Run

A containerised deployment on [Google Cloud](https://en.wikipedia.org/wiki/Google_Cloud_Platform) [Run](https://cloud.google.com/run/) of the [Java implemenation](/implementation) includes a user interfaces for interactive usage of the [GEO Label API](/api): [https://glbservice-nvrpuhxwyq-ew.a.run.app/glbservice/](https://glbservice-nvrpuhxwyq-ew.a.run.app/glbservice/)

Example API URL: [https://glbservice-nvrpuhxwyq-ew.a.run.app/glbservice/api/v1/svg?metadata=https://raw.githubusercontent.com/nuest/GEO-label-java/master/server/src/test/resources/4.0/DigitalClimaticAtlas_mt_an_GEOlabel.xml](https://glbservice-nvrpuhxwyq-ew.a.run.app/glbservice/api/v1/svg?metadata=https://raw.githubusercontent.com/nuest/GEO-label-java/master/server/src/test/resources/4.0/DigitalClimaticAtlas_mt_an_GEOlabel.xml)

Resulting label:

![Example GEO Label](https://glbservice-nvrpuhxwyq-ew.a.run.app/glbservice/api/v1/svg?metadata=https://raw.githubusercontent.com/nuest/GEO-label-java/master/server/src/test/resources/4.0/DigitalClimaticAtlas_mt_an_GEOlabel.xml)

### AWS Lambda

A partial implementation with support for SVG generation is deployed on [Amazon Web Services Lambda](https://en.wikipedia.org/wiki/AWS_Lambda) as an extension of the [Java implementation](/implementation).

Example API URL: [https://6x843uryh9.execute-api.eu-central-1.amazonaws.com/glbservice/api/v1/svg?metadata=https://raw.githubusercontent.com/nuest/GEO-label-java/master/server/src/test/resources/4.0/DigitalClimaticAtlas_mt_an_GEOlabel.xml](https://6x843uryh9.execute-api.eu-central-1.amazonaws.com/glbservice/api/v1/svg?metadata=https://raw.githubusercontent.com/nuest/GEO-label-java/master/server/src/test/resources/4.0/DigitalClimaticAtlas_mt_an_GEOlabel.xml)

Resulting label:

![Example GEO Label](https://6x843uryh9.execute-api.eu-central-1.amazonaws.com/glbservice/api/v1/svg?metadata=https://raw.githubusercontent.com/nuest/GEO-label-java/master/server/src/test/resources/4.0/DigitalClimaticAtlas_mt_an_GEOlabel.xml)

----------

## References

- Graupner A., Nüst, D. 2020. **Serverless GEO Labels for the Semantic Sensor Web**. 11th International Conference on Geographic Information Science (GIScience 2021) - Part I. [https://doi.org/10.4230/LIPIcs.GIScience.2021.I.4](10.4230/LIPIcs.GIScience.2021.I.4)
- Lush, V. 2015. **Visualisation of quality information for geospatial and remote sensing data: providing the GIS community with the decision support tools for geospatial dataset quality evaluation** ([PhD thesis](https://research.aston.ac.uk/en/studentTheses/visualisation-of-quality-information-for-geospatial-and-remote-se))
- Lush V., Bastin L., Lumsden J. 2013. **Developing a GEO Label**, GISRUK. ([paper](http://www.geos.ed.ac.uk/~gisteac/proceedingsonline/GISRUK2013/gisruk2013_submission_44.pdf))
- Nüst, D., & Lush, V. 2015. **A GEO label for the Sensor Web**. [https://doi.org/10.31223/osf.io/ka38z](https://doi.org/10.31223/osf.io/ka38z) ([short paper](https://agile-online.org/Conference_Paper/cds/agile_2015/shortpapers/115/115_Paper_in_PDF.pdf) at the 18th AGILE International Conference on Geographic Information Science, Lisbon, Portugal)

For further references see also the [official GEO Label website](http://www.geolabel.info/references.htm).
