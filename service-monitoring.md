# Service Monitoring

## Individual service

Daemons can be monitored by different means, here listed by order of preference:
1. Using a client lib to perform a functional check
2. Check a network response on the service port
3. Check the process on the server

## Integrated chain 

In order to validate the chain of services that are required for the application, a special endpoint is developped. This endpoint connects to all services and perform a minimal request to validate that the service is functional. The endpoint gives an OK response or the faulty service.

## Application

### Basic test

A basic applicative test is performed, like a landing url http response code. This test is performed as frequently as possible without generating to much stress to the platform (every 30 to 60s). This allows to extract two metrics: response time and availability.

### Advanced scenario

An advanced functional scenario recreates a representative user experience on the application. Application response are validated against predefined pattern to verify most or all functions of the application.


## Usual service probes

### Global web service (external probe)

- Landing page (HTTP 200 response code)
- SSL certificate validity

### High Availability ( HA Proxy / Keepalived )

- Service status
- Listening port
- VIP status
- Frontend status
- Backend status
	- Backend UP/DOWN
	- Number of servers in backend

### Web Server ( Nginx / Apache / PHP)

- Service status
- Listening port
- Available workers
- Number of connections

### Database Server ( MySQL / MariaDB / PgSQL / Redis )

- Service status
- Listening port
- Number of connections
- Replication status
