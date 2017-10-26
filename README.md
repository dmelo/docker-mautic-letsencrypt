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

Mind the fact that, if you change the `letscript/mautic.conf` file you will have
to manually copy it to letsencrypt-config volume
(dockermauticletsencrypt\_mautic-data).

Moreover, the Mautic container will automatically recognize the URL as
`http://mautic` because that is its address, behind the letsencrypt container.
To change it to your actual URL, go to Settings > Configuration, edit the site
URL to the actual value and ppply the changes. Enter the container and clear the
cache:

```sh
docker exec -ti dockermauticletsencrypt_mautic_1 /bin/bash
php app/console cache:clear
```

