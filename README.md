# InterUSS automated testing interfaces

This repository houses the interfaces a USS/USSP must implement in order to be tested by certain scenarios in [the InterUSS automated testing tool uss_qualifier](https://github.com/interuss/dss/tree/master/monitoring/uss_qualifier).

## Interfaces

* [Geo-awareness](geo-awareness/README.md) (DEPRECATED; see [Geospatial map](geospatial_map) instead)
  * [v1 YAML](geo-awareness/v1/geo-awareness.yaml)
* [Geospatial map](geospatial_map/README.md)
  * [v1 YAML](geospatial_map/v1/geospatial_map.yaml) 
* [Remote ID](rid/README.md)
  * Injection (for NetRID Service Providers)
    * [v1 YAML](rid/v1/injection.yaml)
  * Observation (for NetRID Display Providers/Display Applications)
    * [v1 YAML](rid/v1/observation.yaml)
* [SCD](scd/README.md) (will be deprecated; see [flight planning](flight_planning) instead)
  * [v1 YAML](scd/v1/scd.yaml)
* [Flight planning](flight_planning/README.md)
  * [v1 YAML](flight_planning/v1/flight_planning.yaml)
