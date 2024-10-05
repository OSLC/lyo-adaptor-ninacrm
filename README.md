# lyo-adaptor-ninacrm

[![](https://img.shields.io/badge/project-Eclipse%20Lyo-blue?color=418eeb)](https://github.com/eclipse/lyo)
[![CI](https://github.com/OSLC/lyo-adaptor-ninacrm/actions/workflows/main.yml/badge.svg)](https://github.com/OSLC/lyo-adaptor-ninacrm/actions/workflows/main.yml)
[![Discourse users](https://img.shields.io/discourse/users?color=28bd84&server=https%3A%2F%2Fforum.open-services.net%2F)](https://forum.open-services.net/)

> This repository supersedes the 'ninacrm' folder in `lyo.docs` (https://github.com/eclipse/lyo.docs/tree/master/ninacrm)

## Overview

NinaCRM is a fictional CRM application that does not belong to OSLC AM/CM/RM/QM domains. Instead, it represents an example of how OSLC AM/CM/RM/QM apps (adaptors) can be used by (integrated with) non-OSLC AM/CM/RM/QM systems.

## Getting started

Run

```
mvn clean jetty:run
```

Open http://localhost:8181/ninacrm/

To use the "Create Defect..." or "Select Defect..." links, the OSLC RefImpl CM server shall be running (see [docs](https://github.com/oslc-op/refimpl#using-jetty-based-containers-with-docker)).

The "Add Link" link button works correctly only with the servers that have CSP and CORS set up.
