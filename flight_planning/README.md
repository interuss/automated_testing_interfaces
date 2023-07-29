# Flight planning automated testing interface

This folder contains the [USSP interface for flight planning automated testing](v1/flight_planning.yaml).

## Overview

This interface is designed to support the following scenario:
> I (the test director, acting like a normal client operator) want to
> 
> * Plan a flight with the specified characteristics
> * Update an existing flight plan to the new specified characteristics
> * Close an existing flight plan
>
> You (the USSP under test) attempt to fulfill this request, in the same way as if a normal client operator made the same request, and indicate the result.

It also supports other actions likely associated with tests involving flight planning, such as the test director requesting and ensuring that the USSP under test has loaded a particular geospatial dataset.

This interface supports testing of the U-space Flight Authorisation service and other similar services.

## Viewing locally
To view a description of this interface locally, from this folder:

```shell script
docker run -it --rm -p 8080:8080 \
  -v $(pwd)/:/usr/share/nginx/html/api/ \
  -e PORT=8080 -e SPEC_URL=./api/v1/flight_planning.yaml redocly/redoc
```

...then visit [http://localhost:8080/](http://localhost:8080/) in a browser.
