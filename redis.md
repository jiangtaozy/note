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

- Docker run redis-cli

      docker exec -it chs-wfx-redis redis-cli

- Set expire time

      client.set(key, value, 'EX', 60 * 60 * 24, callback);
      // EX seconds -- Set the specified expire time, in seconds.
      // PX milliseconds -- Set the specified expire time, in milliseconds.
      // NX -- Only set the key if it does not already exist.
      // XX -- Only set the key if it already exist.

- Allowing remote connection to redis

      sudo vim /etc/redis/redis.conf
      Comment out the following line
      bind 127.0.0.1
      Restart redis.
      sudo /etc/init.d/redis-server restart
