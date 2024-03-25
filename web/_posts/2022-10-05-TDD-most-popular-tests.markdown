---
layout: post
title:  "TDD Most Popular Tests"
date:   2022-10-05 00:00:00 +0200
categories: ["test_driven_development"]
author: Samuel López Saura & Guillermo Martínez Esteban
permalink: "/test-driven-development-most-popular-tests"
---

# Unit tests

Low level tests created to check a specific funcionality of the code. It
should work isolated, not depending on other functions of the aplication.
Passing unit tests must always be the first step.

# Integration tests

Integration tests checks if the communication between multiple components is
working. For instance, a integration test could validate if the backend can
make queries in a database.

# Functional tests

They check the behaviour of the application in a high level approach.
Functional tests are black boxes, with an input and an expected result,
no matter what happened inside the application.

# End-to-end tests

These tests checks use cases in a real world scenario replicating the
user behaviour if needed. They need a fully working application.

# Regression tests

Tests that checks features developed on previous versions. Their main
goal is to confirm everything is working as expected before the changes
of a new version.

# Smoke testing

They test if minimal features are working. Errors discovered with them must be priorized because any fail means something critical is not working.

# Acceptance testing

Acceptance testing validate that the application fit the requirements defined with the customer. All other tests must have passed before checking acceptance testing.

# Performance testing

Check the behaviour in high load situations. These tests recover metrics and stats.

Examples:

- Junit
- Pytest
- NUnit

![Execution time tests](/assets/images/05_10_execution_time_tests.png)


[Test Driven Development Index]({% post_url 2022-10-05-Test-Driven-Development %})
