# Flight planning automated testing interface

This folder contains the [USSP interface for flight planning automated testing](v1/flight_planning.yaml).

## Overview

In a manual checkout involving flight planning, the test director must interact with USSs under test to cause the USSs to behave in particular ways required for the tests.  Examples of these interactions may include:

1. "USS X, is your system ready to be tested?"
2. "USS X, please prepare for the test by making sure any pre-existing flights in the area are closed so that the test area is clear.  Can you confirm that the area is clear of any flights, operational intents, or other artifacts that you manage?"
3. "USS X, please plan the yellow flight described on the test card.  Was that planning attempt successful?"
4. "USS X, please cancel the yellow flight.  Was the flight canceled successfully?"
5. "USS X, please start flying the yellow flight.  Was authorization to start flying successful?"
6. "USS X, please land and close the yellow flight.  Was the flight closed successfully?"
7. "USS X, it looks like something went wrong; please delete the yellow flight so we can continue the test.  Were you able to delete it?"

This interface is designed to support automation of the interactions above, and interactions similar to them.

These interactions fall into one of two categories:

* The test director is instructing a USS representative to use the USS system normally.  In this case, it could be that the USS representative is not from the USS company at all, but merely a third party contracted to assist with the test by using the USS's system as they were trained.  The scope `interuss.flight_planning.plan` is used for these operations.  The USS's handler for these operations should only perform actions that a normal user of the system could perform.  Examples include:
    * Planning a future flight
    * Starting to fly under a flight plan
    * Landing and closing a flight plan
    * Canceling a flight plan
* The test director is coordinating the test itself, performing actions that normal users of the USS could not generally perform.  The scope `interuss.flight_planning.direct_automated_test` is used for these operations.  Examples include:
    * Determining system readiness
    * Clearing existing artifacts from the system
        * Note that most of the actions that will usually be performed here should be possible for a normal user.  Specifically, the normal user would simply identify all their flights in the specified area and close them normally.  However, there are edge cases where residual flight artifacts may not have been cleaned up normally and this handler is where the USS should attempt to perform cleanup.  For instance, when performing ASTM F3548-21 SCD, a USS may accidentally fail to delete one or more operational intents they manage when deleting the flights as a normal user would.  In this case, the USS should then query the DSS to identify any operational intents in the area that they manage and administratively remove these operational intents assuming they are not linked to any flight known to the USS.  If the USS fails to clear certain artifacts (especially F3548 operational intents) that they manage, the test will often be unable to proceed.
    * Forcibly deleting a flight that couldn't be closed normally

## Viewing locally
To view a description of this interface locally, from this folder:

```shell script
docker run -it --rm -p 8888:8888 \
  -v $(pwd)/:/usr/share/nginx/html/api/ \
  -e PORT=8888 -e SPEC_URL=./api/v1/flight_planning.yaml redocly/redoc
```

...then visit [http://localhost:8080/](http://localhost:8080/) in a browser.
