# opa-sandbox
Testing out opa

## Things you will need
- docker
- docker-compose
- opa cli (optional)

### Resources
- https://www.openpolicyagent.org/docs/latest/#running-opa
- https://www.openpolicyagent.org/docs/latest/deployments/

## Getting Started
First you will need to get OPA running locally. For this we will use docker-compose to make sure things are nice and simple
```
docker-compose up -d
```
_if you would like to start from scratch_
```
docker-compose down
```
Then test that it is up and running
```
curl localhost:8500/v1/data/foo/bar
> {}
```

### Setting Up Policies
We can use the OPA [Rest API](https://www.openpolicyagent.org/docs/latest/rest-api/) to upload our policies via
```
curl -X PUT localhost:8500/v1/policies/{id} --data-binary "@example.rego"
```
And if you would like to check the current state of a policy
```
curl localhost:8500/v1/policies/{id}
```
or delete the polict
```
curl -X DELETE localhost:8500/v1/policies/{id}
```


