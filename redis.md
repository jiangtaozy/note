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
