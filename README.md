# lyo-adaptor-ninacrm

[![](https://img.shields.io/badge/project-Eclipse%20Lyo-blue?color=418eeb)](https://github.com/eclipse/lyo)
[![CI](https://github.com/OSLC/lyo-adaptor-ninacrm/actions/workflows/main.yml/badge.svg)](https://github.com/OSLC/lyo-adaptor-ninacrm/actions/workflows/main.yml)
[![Docker](https://github.com/OSLC/lyo-adaptor-ninacrm/actions/workflows/docker.yml/badge.svg)](https://github.com/OSLC/lyo-adaptor-ninacrm/actions/workflows/docker.yml)
[![Discourse users](https://img.shields.io/discourse/users?color=28bd84&server=https%3A%2F%2Fforum.open-services.net%2F)](https://forum.open-services.net/)

> **This repository has been superseed by a https://oslc.github.io/oslc-selection-utils/ that provide an easy-to-use WebComponent to pick an OSLC resource link from another OSLC server.**

> This repository supersedes the 'ninacrm' folder in `lyo.docs` (https://github.com/eclipse/lyo.docs/tree/master/ninacrm)

## Overview

NinaCRM is a fictional CRM application that does not belong to OSLC AM/CM/RM/QM domains. Instead, it represents an example of how OSLC AM/CM/RM/QM apps (adaptors) can be used by (integrated with) non-OSLC AM/CM/RM/QM systems.

## Getting started

### Running with Maven

Run

```
mvn clean jetty:run
```

Open http://localhost:8181/ninacrm/

### Running with Docker

You can also run the application using Docker:

```bash
# Build and run with docker-compose (recommended)
docker-compose up --build

# Or build and run manually
docker build -t ninacrm .
docker run -p 8181:8181 ninacrm
```

The application will be available at http://localhost:8181/

To stop the application:
```bash
# If using docker-compose
docker-compose down

# If running manually
docker stop <container-id>
```

### Pre-built Docker Images

Pre-built Docker images are available from GitHub Container Registry for both x86_64 (amd64) and ARM64 architectures:

```bash
# Run the latest version
docker run -p 127.0.0.1:8181:8181 ghcr.io/oslc/lyo-adaptor-ninacrm:latest

# Run a specific version
docker run -p 127.0.0.1:8181:8181 ghcr.io/oslc/lyo-adaptor-ninacrm:0.1.0
```

> **Note:** Images are automatically rebuilt weekly to ensure the latest security updates from base images.

## Usage

### Testing OSLC Integration

To use the "Create Defect..." or "Select Defect..." links, you'll need the OSLC RefImpl CM server running. You have two options:

**Option 1: Enable in docker-compose (easiest)**
1. Edit `docker-compose.yml` and uncomment the `oslc-refimpl` service section
2. Run: `docker-compose up --build`
3. NinaCRM will be available at http://localhost:8181/
4. OSLC RefImpl will be available at http://localhost:8800/
5. Use `http://localhost:8800/services/rootservices` as the root services URI in NinaCRM

**Option 2: Run OSLC RefImpl separately**
Follow the [OSLC RefImpl documentation](https://github.com/oslc-op/refimpl#using-jetty-based-containers-with-docker) to run it separately.

### Notes

The "Add Link" link button works correctly only with servers that have CSP and CORS set up.
