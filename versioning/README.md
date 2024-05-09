# Versioning automated testing interface

## Purpose

The goal of automated testing is to verify that a system under test meets desired sets of requirements.  The primary statement a test participant generally wants to make after successfully completing an automated test run is that their system under test has been verified to be compliant with one or more particular sets of requirements.  But, this statement begs the question of which system was under test.

The API is intended to allow USSs or their representatives to identify the exact system under test (by reporting its version) at the time the test is conducted.  Under typical release practices, a release candidate would be required to pass automated tests in a qualification environment before being promoted to production.  Under those practices, the expectation would be that the version of software in production always matches a version with a passing test report in the qualification environment.  This interface provides the means by which that version can be determined both in the qualification environment during test and in production (for verification of these release practices).

## Overview

[This API](versioning.yaml) is designed to enable USSs or their representatives to respond to the question, "What version of the USS system is running?"  This question is complicated by the fact that a USS or their representative needs a clear definition of the scope of "system" in order to answer the question meaningfully.  Rather than try to create that system scope/boundary definition itself, this API resolves this question by allowing the questioner to refer to a system boundary definition defined external to this interface but known to both the USS/representative and the questioner.
