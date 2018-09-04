# Docker Proxy
Vagrant &amp; docker deployment of [mitmproxy](https://mitmproxy.org/) for local development of proxy servers  
The proxy can be accessed via 192.168.1.00:8080 from the host.
For ease of use I recommend modifying hosts to resolve proxy to 192.168.1.10

## Requirements
- [Vagrant](https://www.vagrantup.com/)
- [Docker](https://docs.docker.com/install/)

## Usage
From the root of the repo
```
vagrant up
vagrant ssh
docker run --rm -it -p 8080:8080 mitmproxy/mitmproxy mitmdump
```
