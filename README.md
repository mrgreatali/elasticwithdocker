# Elastic Stack with Docker

##Installation
Run following commands to execute elastic stack on server
```bash
docker-compose -f create-certs.yml run --rm create_certs

docker-compose -f docker-compose-secure-single-instance.yml up -d

docker exec es01 /bin/bash -c "bin/elasticsearch-setup-passwords \
auto --batch --url http://es01:9200"

```