# InterUSS automated testing interfaces

This repository houses the interfaces a USS/USSP must implement in order to be tested by certain scenarios in [the InterUSS automated testing tool uss_qualifier](https://github.com/interuss/dss/tree/master/monitoring/uss_qualifier).

## Interfaces

* [Geo-awareness](geo-awareness/README.md)
  * [v1 YAML](geo-awareness/v1/geo-awareness.yaml)
* [Remote ID](rid/README.md)
  * Injection (for NetRID Service Providers)
    * [v1 YAML](rid/v1/injection.yaml)
  * Observation (for NetRID Display Providers/Display Applications)
    * [v1 YAML](rid/v1/observation.yaml)
* [Flight planning](scd/README.md)
  * [v1 YAML](scd/v1/scd.yaml)
