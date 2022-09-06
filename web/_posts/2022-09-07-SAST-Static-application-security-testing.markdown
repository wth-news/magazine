---
layout: post
title:  "SAST - Static Application Security Testing"
date:   2022-08-07 00:00:00 +0200
permalink: /sast-static-application-security-testing
author: Guillermo Martínez Esteban & Samuel López Saura
categories:
---

# Summary

Static Application Security Testing (SCA)  analyse the source code of your
application searching for programming errors and insecure code.

# Use cases

- Analyze our source code to:
- Find programming errors.
- Discover vulnerabilities.
- Detect the usage of dangerous methods.

# Description

SAST are tools that perform  static code analysis in order to find
vulnerabilities.

While SAST could be a bit slow and don't check code in runtime, they are good
solutions to discover bad habits in source code. Each line is checked and
useful information is showed if something is not properly written.

SAST tools should be used frequently during the development. That way,
potential security breaches can be quickly fixed, even before new version
deploy.

Most of SAST use Abstract Syntax Tree (AST). AST transform programming code in
models which could be easily follow by a analyzer. Once SAST has a model, it
could be tested to found known issues.

Results of static analysis must be manually confirmed. SAST could detect false
positives that can not be automatically discarded. This could be mitigated
analizying the code frequently. Some SAST could be integrated with IDE, which
is a really good help for developers.

# Proof of concept

One SAST solution is bandit, an open source static analyzer for Python. It is
very popular and easy to install in Linux machines.

The following code has an important flaw because a malicious user could execute
arbitrary coommands.

{% highlight python %}
import os
ip = input('Insert IP: ')
os.system('ping %s' % ip)
{% endhighlight %}

Executing bandit agains our source code: 

![Bandit shell output](/assets/images/07_09_bandit_output.png)

Exporting bandit results to a CSV:

{% highlight bash %}
$ bandit -r test.py -o output.csv
{% endhighlight %}

![Bandit CSV output](/assets/images/07_09_bandit_csv.png)

# Other tools enumeration

- Brakeman
- Checkmarx
- AppSweep
- Kiwuan

# Conclusion

- SAST tools can find programming errors and discover vulnerabilities in our
  source code.
- Static analysis could have important costs of time, so each execution have to
  be carefully managed.
- It is very useful to execute a  SAST tool  before making a release or a merge
  request.
- Results have to be checked in order to discard false positives.
- SAST tools can have a high number of false positives.

[Automatic Vulnerability Search Index]({% post_url 2022-09-07-Automatic-vulnerability-search %})
