# Consul Service Discovery with Nginx Load Balancer

This project demonstrates service discovery using Consul and load balancing with Nginx on AWS EC2.

## Architecture

Users → Nginx Load Balancer → Backend Servers

Consul is used for:

- Service registration
- Health checks
- Dynamic service discovery

## Infrastructure

- AWS EC2
- Consul Server
- Backend1 (Nginx)
- Backend2 (Nginx)
- Nginx Load Balancer

## Features

- Multi-node Consul cluster
- Automatic service registration
- Health checks
- Reverse proxy load balancing
- Dynamic backend discovery

## Commands Used

### Start Consul Agent

consul agent -node=backend1 -data-dir=/tmp/consul -bind=0.0.0.0

### Register Service

consul services register web.json

### Verify Services

consul catalog nodes -service nginx-web
