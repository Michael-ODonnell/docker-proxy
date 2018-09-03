# Docker Proxy
Vagrant &amp; docker deployment of [mitmproxy](https://mitmproxy.org/) for local development of proxy servers  
The proxy can be accessed via 192.168.1.100:5000 from the host.
For ease of use I recommend modifying hosts to resolve proxy to 192.168.1.100

## Requirements
- [Vagrant](https://www.vagrantup.com/)
- [Docker](https://docs.docker.com/install/)

## Usage
From the root of the repo
```
vagrant up
vagrant ssh
docker run --rm -it -p 5000:8080 mitmproxy/mitmproxy mitmdump
```

For a web interface running on http://192.168.1.100 instead of the interactive console, use
```
docker run --rm -it -p 5000:8080 -p 192.168.1.100:80:8081 mitmproxy/mitmproxy mitmweb --web-iface 0.0.0.0
```
