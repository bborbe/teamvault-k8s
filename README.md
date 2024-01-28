# Teamvault K8s Deployment

## Copy Postgres

```
docker pull --platform=linux/amd64 postgres:10.5
docker tag postgres:10.5 fire.hm.benjamin-borbe.de:5000/postgres:10.5
docker push fire.hm.benjamin-borbe.de:5000/postgres:10.5
```

## Build Teamvault

```
cd teamvault-docker
REGISTRY=fire.hm.benjamin-borbe.de:5000 IMAGE=teamvault make build upload
```

## Build OpenLDAP

```
cd openldap-docker
REGISTRY=fire.hm.benjamin-borbe.de:5000 IMAGE=openldap make build upload
```
