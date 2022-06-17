# SETUP sso use symfony

## install symfony
- create composer.json
- run ```composer install```

## install doctrine 

follow instruction [here](https://symfony.com/doc/current/doctrine.html#installing-doctrine)

resolve issue : https://github.com/starganteknologi/sso/issues/2

## install OAuth2 Server Bundle

```shell
composer require league/oauth2-server-bundle
``` 

follow instruction [here](https://github.com/thephpleague/oauth2-server-bundle/blob/master/docs/index.md#installation) 

### Generating public and private keys

generate public and private keys for oauth2 server. you can follow instruction [here](https://oauth2.thephpleague.com/installation/#generating-public-and-private-keys)

``` shell
openssl genrsa -out privateOauth2.key 2048
openssl rsa -in privateOauth2.key -pubout -out publicOauth2.key
```

copy both files to your certs folder, in my case ```/etc/ssl/certs```

### Generating encryption keys

#### string password

```shell
php -r 'echo base64_encode(random_bytes(32)), PHP_EOL;'
```

#### Key object

```shell
vendor/bin/generate-defuse-key
```
