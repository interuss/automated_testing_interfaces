# Flight planning automated testing interface

---
Note: This interface will be DEPRECATED and REMOVED.  The replacement interface will be the [flight planning interface](../flight_planning).

---

This folder contains the [USSP interface for flight planning automated testing](v1/scd.yaml).

## Overview

This interface is designed to support the following scenario:

> The test director indicates to the USSP that there is a user intent to create a flight with certain specified characteristics.  The USSP responds to this intent appropriately and creates the flight or does not create the flight according to the circumstances.

This interface enables testing of most parts of ASTM F3548-21 and the U-space Flight Authorisation service, and other similar services.

The intent of this interface is to impose as few additional requirements on USSP implementations as practical, but some additional capabilities are also needed to ensure complete and reliable test runs:

### Capabilities

A USSP must report the flight-planning capabilities it supports so that optional capabilities will not be tested.

### Area clearing

It is important for the test area to be free of existing flights, so the USSP must support the ability to clear/remove whatever flights it may currently be managing within a specified area.

## Viewing locally
To view these YAML files locally:

```shell script
docker run -it --rm -p 8080:8080 \
  -v $(pwd)/v1/geo-awareness.yaml:/usr/share/nginx/html/swagger.yaml \
  -e PORT=8080 -e SPEC_URL=swagger.yaml redocly/redoc
```

...then visit [http://localhost:8080/](http://localhost:8080/) in a browser.
