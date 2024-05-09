# Geospatial map automated testing interface

This folder contains the [USSP interface for geospatial map automated testing](v1/geospatial_map.yaml).

## Overview

This interface is designed to support the following scenario:
> If a normal client operator were to "view" the geospatial map of the USSP under test at this specific point, would the map contain any applicable geospatial features at that point?

It also supports other actions likely associated with tests involving geospatial maps, such as the test director requesting and ensuring that the USSP under test has loaded a particular geospatial dataset.

This interface supports testing of the U-space Geo-Awareness service and other similar services.

It has been designed to impose minimal additional requirements on USSP implementations.
[See discussion for details](https://github.com/interuss/dss/pull/809#discussion_r982930704)

## Viewing locally
To view a description of this interface locally, from this folder:

```shell script
docker run -it --rm -p 8888:8888 \
  -v $(pwd)/:/usr/share/nginx/html/api/ \
  -e PORT=8888 -e SPEC_URL=./api/v1/geospatial_map.yaml redocly/redoc
```

...then visit [http://localhost:8080/](http://localhost:8888/) in a browser.
