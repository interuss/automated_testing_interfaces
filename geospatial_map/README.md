# Geospatial map automated testing interface

This folder contains the [USSP interface for geospatial map automated testing](v1/geospatial_map.yaml).

## Overview

This interface is designed to support the following scenario:
> If I (the test director, acting like a normal client operator) were to "view" your (the USSP under test) geospatial map at this specific point, would you (the USSP under test) indicate that there are any applicable geospatial features on the map at that point?

It also supports other actions likely associated with tests involving geospatial maps, such as the test director requesting and ensuring that the USSP under test has loaded a particular geospatial dataset.

This interface supports testing of the U-space Geo-Awareness service and other similar services.

It has been designed to impose minimal additional requirements on USSP implementations.
[See discussion for details](https://github.com/interuss/dss/pull/809#discussion_r982930704)

## Viewing locally
To view a description of this interface locally, from this folder:

```shell script
docker run -it --rm -p 8080:8080 \
  -v $(pwd)/:/usr/share/nginx/html/api/ \
  -e PORT=8080 -e SPEC_URL=./api/v1/geospatial_map.yaml redocly/redoc
```

...then visit [http://localhost:8080/](http://localhost:8080/) in a browser.
