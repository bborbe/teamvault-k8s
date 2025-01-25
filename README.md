# Teamvault K8s Deployment

## Copy Postgres

```
docker pull --platform=linux/amd64 postgres:10.5
docker tag postgres:10.5 docker.quant.benjamin-borbe.de:443/postgres:10.5
docker push docker.quant.benjamin-borbe.de:443/postgres:10.5
```

## Build Teamvault

```
cd teamvault-docker
REGISTRY=docker.quant.benjamin-borbe.de:443 IMAGE=teamvault make build upload
```

## Build OpenLDAP

```
cd openldap-docker
REGISTRY=docker.quant.benjamin-borbe.de:443 IMAGE=openldap make build upload
```
