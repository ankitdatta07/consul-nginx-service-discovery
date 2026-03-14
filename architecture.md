# Architecture

This project demonstrates dynamic service discovery using **Consul** with **Nginx load balancing** on **AWS EC2**.

## System Architecture
                +-------------+
                |   Users     |
                +-------------+
                       |
                       v
              +------------------+
              |   Nginx Server   |
              |   Load Balancer  |
              +------------------+
                       |
        +--------------+--------------+
        |                             |
        v                             v
  +-------------+              +-------------+
  |  Web Node 1 |              |  Web Node 2 |
  |  EC2        |              |  EC2        |
  +-------------+              +-------------+
        |                             |
        +-------------+---------------+
                      |
                      v
              +----------------+
              |  Consul Server |
              | Service Registry|
              +----------------+
              ## Architecture Flow

1. Users send requests to the Nginx load balancer.
2. Nginx distributes traffic to available web servers.
3. Web servers register themselves with Consul.
4. Consul maintains a dynamic service registry.
5. When nodes join or leave, Nginx updates upstream servers automatically using Consul service discovery.
