# Redis tutorial


### install

#### via docker

```bash
docker run -d --name redis-stack -p 6379:6379 -p 8001:8001 redis/redis-stack:latest
```

#### via MAC homebrew (unfortunately you have to install it for the cli)

```bash
brew install redis
```

### Connect 

#### Using docker

Attach to container and execute redis-cli command
```bash
docker exec -it redis-stack redis-cli
```

### Connect using redis-cli

```bash
redis-cli -h host -a ${password } -p port
```

### Bulk upload

Add records to file load-set-test.txt
```shell
SADD cybersource:test:set 0136432299151234
SADD cybersource:test:set 0136432299151235
SADD cybersource:test:set 0136432299151236
```

```shell
cat load-set-test.txt | redis-cli --pipe
```

### Reference

- [basic CLI commands](https://developer.redis.com/howtos/quick-start)
- [data-types](https://redis.io/docs/data-types)