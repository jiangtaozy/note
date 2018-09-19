- Delete all the keys of all the existing databases, not just the currently selected one. This command never fails.

      flushall

-  List all keys stored in redis.

      keys *

- Select database

      select 1

- Sets the specified fields to their respective values in the hash stored at key

      HMSET myhash field1 "Hello" field2 "World"

- all fields and values of the hash

      HGETALL myhash

- How to atomically delete keys matching a pattern

    EVAL "return redis.call('del', unpack(redis.call('keys', ARGV[1])))" 0 prefix:*

- Docker run redis

    docker run -it --link some-redis:redis --rm redis redis-cli -h redis -p 6379
