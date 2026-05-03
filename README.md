# Monitoring Stack for Coolify

## Description

A collection of containers designed to gather system-level metrics and metrics from all running containers.  
The stack was later enhanced with log collection using Vector, providing a unified solution for metrics and log aggregation.

## Stack
**Metrics (Host)**: Prometheus Node Exporter  
**Metrics (Containers)**: cAdvisor  
**Logs**: Vector  

## Environment Variables

The following environment variables must be provided:

**NODE_NAME** — the name of the server (used for identifying metrics and logs)  
**VICTORIALOGS_ENDPOINT** — the address of the VictoriaLogs instance in the format: `<hostname>:<port>`

## How It Works
**[Node Exporter](https://github.com/prometheus/node_exporter)** collects system-level metrics such as CPU, memory, disk, and network usage.  
**[cAdvisor](https://github.com/google/cadvisor)** gathers metrics from all running containers.  
**[Vector](https://github.com/vectordotdev/vector)** collects and processes logs from containers for centralized aggregation.  