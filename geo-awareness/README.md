# Geo-Awareness automated testing interface

---
Note: This interface is DEPRECATED and will be REMOVED.  The replacement interface is the [geospatial map interface](../geospatial_map).

---

This folder contains the [USSP interface for Geo-Awareness automated testing](v1/geo-awareness.yaml).

## Overview

This interface is designed to support the following scenario:
> If I (the test director, acting like a normal client operator) were to request information at this specific point, would you (the USSP under test) indicate that there are any applicable operational conditions or airspace constraints, relevant UAS geographical zones, or applicable temporary restrictions.

This interface supports testing of the U-space Geo-Awareness service and other similar services.

It has been designed to impose minimal additional requirements on USSP
implementations.
[See discussion for details](https://github.com/interuss/dss/pull/809#discussion_r982930704)

A USSP wishing to qualify its service using a test suite requiring this
interface must implement the
[USSP interface for Geo-Awareness automated testing](v1/geo-awareness.yaml).

## Viewing locally
To view these YAML files locally:

```shell script
docker run -it --rm -p 8080:8080 \
  -v $(pwd)/v1/geo-awareness.yaml:/usr/share/nginx/html/swagger.yaml \
  -e PORT=8080 -e SPEC_URL=swagger.yaml redocly/redoc
```

...then visit [http://localhost:8080/](http://localhost:8080/) in a browser.
