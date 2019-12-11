# `docker-compose` `pretix/standalone`

```sh
sudo useradd --no-create-home --uid 15371 pretixuser
docker-compose up --detach
sudo chown -R pretixuser:pretixuser data/pretix
```

```sh
docker-compose exec pretix python /pretix/src/manage.py migrate
docker-compose exec pretix python /pretix/src/manage.py compress
docker-compose exec pretix python /pretix/src/manage.py collectstatic --no-input
```

