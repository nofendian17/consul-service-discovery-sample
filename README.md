# golang-service-discovery

This is a simple example to integrate golang services to Consul. This repo cover how golang services register its self to Consul, discover service when a service need to call another service, provide a healthcheck api to be consumed by Consul, and get Key Value (KV) store that we populate in Consul UI and consumed by golang services.

# How to run
- Make sure docker is already installed on your machine
- Change directory to deploy
- *docker-compose-build*
- *docker-compose up*
- add consul KV product-service with name *(product-configuration)*
```
{
	"categories" : ["one", "two", "three", "four"]
}
```

- check endpoint http://localhost:8100/products, http://localhost:8100/product-configuration, http://localhost:8100/healthcheck

ref : https://medium.com/amartha-engineering/leveraging-consul-as-service-discovery-health-checking-and-key-value-kv-store-in-go-e475cf63ab6a