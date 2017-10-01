# Mautic with Letsencrypt

Copy the `.env.template` to `.env` and replace the values of `.env` accordingly:

```sh
cp .env.template .env
vim .env
```

Do the same proocedure with `letsencrypt/mautic.conf.template`:

```sh
cp letsencrypt/mautic.conf.template letsencrypt/mautic.conf
vim letsencrypt/mautic.conf
```

Run the docker-compose:

```sh
docker-compose build
docker-compose up
```
