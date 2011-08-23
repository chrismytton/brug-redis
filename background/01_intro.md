!SLIDE bullets incremental

# What is redis not?

* **not** SQL
* **not** a document store
* **not** a bigtable store

!SLIDE bullets incremental

# What is redis?

* key-value store
* data-structures server
* fast, *very* fast

!SLIDE incremental commandline

## Key-value store
    @@@
    $ redis-cli set 'user:481:ip_address' '192.168.0.240'
    OK

    $ redis-cli get 'user:481:ip_address'
    "192.168.0.240"
