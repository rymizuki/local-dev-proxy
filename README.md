# local-dev-proxy

## setup

### create sites-available

```conf:services/nginx/sites-available/example.localhost
{
  server_name example.localhost

  location / {
    proxy_pass http://host.docker.internal:3000/;
  }
}
```

### create sites-enabled

```sh
cd ./services/nginx/sites-enabled
ln -s ../sites-available/example.localhost ./example.localhost
```

## start docker

```sh
docker compose up
```
