!SLIDE title center

# Redis, how does it work?

!SLIDE incremental commandline

## String values

    $ redis-cli set 'name' 'hectic'
    OK
    $ redis-cli get 'name'
    "hectic"
    $ redis-cli append 'name' 'jeff'
    OK
    $ redis-cli get 'name'
    "hecticjeff"

    $ redis-cli set 'user:481:ip_address' '192.168.0.240'
    OK
    $ redis-cli get 'user:481:ip_address'
    "192.168.0.240"

!SLIDE incremental commandline

## Counters

    $ redis-cli incr 'hits'
    (integer) 1
    $ redis-cli incr 'hits'
    (integer) 2
    $ redis-cli incr 'hits'
    (integer) 3
    $ redis-cli get 'hits'
    "3"

!SLIDE incremental commandline

## Lists

    $ redis-cli lpush 'web1:logs', 'INFO web1 - GET / 200 OK'
    OK
    $ redis-cli lpush 'web1:logs', 'INFO web1 - GET /favicon.ico 200 OK'
    OK

    $ redis-cli rpop 'web1:logs'
    "INFO web1 - GET / 200 OK"
    $ redis-cli rpop 'web1:logs'
    "INFO web1 - GET /favicon.ico 200 OK"
