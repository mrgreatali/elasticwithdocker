# Elastic Stack with Docker

##Installation
Run following commands to execute elastic stack on server
```bash

sysctl -w vm.max_map_count=262144

sysctl --system

systemctl restart docker

docker network create elastic --attachable

docker-compose -f create-certs.yml run --rm create_certs

docker-compose -f docker-compose-secure-single-instance.yml up -d

docker exec esmaster /bin/bash -c "bin/elasticsearch-setup-passwords \
auto --batch --url http://esmaster:9200"

```