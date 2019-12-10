# `docker-compose` `pretix/standalone`

```sh
sudo useradd --no-create-home --uid 15371 pretixuser
sudo chown -R pretixuser:pretixuser data/
docker-compose up --detach
```

```sh
docker-compose exec --user=pretixuser pretix python /pretix/src/manage.py migrate
docker-compose exec --user=pretixuser pretix python /pretix/src/manage.py compress
docker-compose exec --user=pretixuser pretix python /pretix/src/manage.py collectstatic --no-input
```
