---
layout: post
title:  "SCA - Software Composition Analysis"
date:   2022-08-07 00:00:00 +0200
permalink: /sca-software-composition-analysis
categories:
author: Samuel López Saura & Guillermo Martínez Esteban
---

# Summary

Software Composition Analysis (SCA) checks third-party components used within
your application.

# Use cases

Analyze third party components to:

- Find malicious third party components.
- Find vulnerabilities in third party components.
- Avoid legal issues with problematic licenses of third party components.

# Description

SCA tools find security issues by searching reported vulnerabilities for the
components used in your application. SCA-type tools have a very low percentage
of false positives compared to SAST and DAST tools. SCA tools only checks
third-party components. They don’t search vulnerabilities included in your own
code. Some SCAs also checks licenses of components in order to avoid legal
issues by warning you about problematic licenses. The most common ones compare
dependency files with known vulnerabilities for the libraries specified in
these files.

Example dependency files: requirements.txt, Gemfile, package.json

The following file has the content of a dependency file from an application
made with python and django. Each line belongs to a external dependency. We can
see here how the application uses the django version 3.0.7.

{% highlight txt %}
django==3.0.7
djangorestframework==3.11.0
psycopg2-binary==2.8.5
django-cors-headers==3.4.0
{% endhighlight %}

An SCA tool will search security vulnerabilities associated to each
library+version specified in this file.

# Proof of concept


Safety is a SCA designed for Python that can be freely installed by running pip
install safety.
Safety can be run against our project dependencies by specifying the dependency
file: `safety check -r requirements.txt`.

![Safety execution](/assets/images/07_09_safety_execution.png)

[More information about Safety](https://pyup.io/safety/)

Advanced SCA tools could try to fix vulnerabilities automatically. Github
dependabot is and example of this. After finding vulnerabilities in
dependencies it creates a pull request to fix them by upgrading the component
to a higher version where the vulnerability it is expected to be resolved.

![Github dependabot creating an PR to fix a vulnerability found in a dependency.](/assets/images/07_09_github_dependabot_pr.png)

# Other tools enumeration

- OWASP dependency-check
- Snyk
- Sonatype Nexus Lifecycle
- Veracode Software Composition Analysis.

# Conclusion

- SCA tools checks third party components vulnerabilities.  Some of them could
  also check problematic licenses.
- SCA tools don’t search for vulnerabilities introduced in your code.
- SCA tools have a very low false positives ratio.
- SCA execution is fast. If the team has some kind of development pipeline it
  is desirable to add a SCA tool to discover third party vulnerabilities and
resolve them during development.

[Automatic Vulnerability Search Index]({% post_url 2022-09-07-Automatic-vulnerability-search %})
