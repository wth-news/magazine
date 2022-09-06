---
layout: post
title:  "DAST - Dynamic Application Security Testing"
date:   2022-08-07 00:00:00 +0200
permalink: /dast-dynamic-application-security-testing
author: Samuel López Saura & Guillermo Martínez Esteban
categories:
---

# Summary

Dynamic Application Security Testing (DAST) is a manual and automated approach
to discover vulnerabilities by testing an application during its execution.

# Use cases

- Security testing in similar to real world
  scenarios.
- Discover vulnerabilities simulating a real attack.
- Penetration testing.

# Description

DAST tools simulate attacks trying to exploit vulnerabilities in a deployed
application. Their execution can be automated but even automation saves
penetration testers a lot of time this doesn’t replace them. DAST tools test
application workflows searching vulnerabilities through different techniques
like enumeration, fuzzing or execution of exploits for known vulnerabilities.


![Burp Repeater Screenshot](/assets/images/07_09_burp_repeater.png)

DAST tools can have different execution modes in order to search for
vulnerabilities in an automated way or manually. Both modes should be used in
conjunction but they don’t need to be used at the same time. Manual mode can be
used in penetration testing when a release is going to be made and automated
mode can be executed periodically every night.

DAST tools can be integrated inside continuous deployment pipelines to scan
each version of the deployed software.

# Proof of concept

Using BURP we can perform a guided security assessment. In the next picture, a
web request has been sent to the repeater section of BURP and it will be sent
modifying some parameters to test a SQLi vulnerability in the login params. The
modified content its called a payload. A lot of payloads can be tested in an
automatic way for each param using the intruder section of BURP suite. The
usage of this specific tool goes beyond this article. BURP can also works by
itself crawling a web site and testing security vulnerabilities in the
discovered attack surface.

![Burp Repeater POC](/assets/images/07_09_burp_repeater_poc.png)

OWASP ZAP, which is another DAST tool, has a Github action that allows anyone
integrate ZAP scanner in his GitHub continuous deployment pipeline.

![ZAP Github Action](/assets/images/07_09_zap_github_action.png)

[More information about OWASP ZAP Github Action](https://www.zaproxy.org/blog/2020-05-15-dynamic-application-security-testing-with-zap-and-github-actions/)

# Other tools enumeration

- Arachnni-scanner
- Acunnetix
- OWASP ZAP

# Conclusion

- Unlike SCA and SAST, DAST tools are executed against running applications.
- Automatic DAST tools helps finding vulnerabilities in deployed scenarios but
  doesn’t replace penetration testing.
- DAST tools are also used in penetration pesting.
- DAST tools can be added to continue deployment pipelines after the deployment
  of the software.

[Automatic Vulnerability Search Index]({% post_url 2022-09-07-Automatic-vulnerability-search %})
