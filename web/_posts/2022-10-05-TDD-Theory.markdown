---
layout: post
title:  "TDD Theory"
date:   2022-10-05 00:00:00 +0200
categories: ["test_driven_development"]
author: Samuel López Saura & Guillermo Martínez Esteban
permalink: "/test-driven-development-theory"
---

Test Driven Development is a methodology that consists in creating tests for
use cases before writing the code.


TDD helps you write better and maintainable software. They let you know when
you are breaking something while refactoring and adding new features. While
TDD implies adding an extra time during the development of the features it
reduces the time needed to maintain it and to add future features.


On this basis, although it may be desirable, it is not necessary to use TDD
in simple scripts that do not require maintenance. On the other hand, in
maintainable software development TDD becomes desirable. Initial tests can
serve as requirements that can be used to help document the feature being
developed. The old tests serve as a basis to ensure that new features do
not break existing code as well as serve as documentation.


## TDD Flow

Essentially TDD write the tests first and then write code to make the tests pass.

![TDD Flow](/assets/images/05_10_simple_tdd_flow.png)

TDD methodology has the following flow:

- Choose a class/method/use case to develop.
- Write a failing test checking the expected functionality.
- Write the necessary code to makes the test pass.
- Refactor.
- Run the test to check everything is still working.
- Iterate until you're done with that feature.

# Related methodologies

- [Secure Test Driven Development](https://www.linkedin.com/pulse/security-test-driven-development-stdd-surendran-ethiraj)
- [BDD](https://en.wikipedia.org/wiki/Behavior-driven_development)

# Conclusion

Althought the use of TDD is always desirable in small scripts with no
maintenance needed it could be not as cost-effective as in bigger applications.

TDD is a methodoly that creates tests for a feature before writing the code.
Tests are always desirable but if the tests are written after coding features
then TDD is not being applied. Still it is better to write tests after developing
a feature than not to write it at all.

[Test Driven Development Index]({% post_url 2022-10-05-Test-Driven-Development %})
