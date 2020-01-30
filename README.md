# Spring Boot with Kotlin and Reactive Cassandra
Example of Spring Data Cassandra with Reactor.

## Quick start
This guide use ScyllaDB implementation of Cassandra.

First, instantiate a ScyllaDB container.

~~~
    docker run --named scylla-test -p 127.0.0.1:9042:9042 -d scylladb/scylla
    docker start scylla-test
~~~

Install CQL shell (require Python 2):

~~~
    pip install cqlsh
~~~

Connect with Scylla:

~~~
    cqlsh 127.0.0.1 9042
~~~

Check if Scylla actually works:

~~~
    cqlsh> select release_version from system.local;
    
     release_version
    -----------------
               3.0.8
    
    (1 rows)
~~~

To run this project, create a new keyspace named `mykeyspace`:

~~~
    create keyspace mykeyspace with replication = { 'class' : 'SimpleStrategy', 'replication_factor' : 1 };
~~~

Edit `application.properties` accorddingly.

## References
1. Based on [spring-projects/spring-data-examples](https://github.com/spring-projects/spring-data-examples/tree/master/cassandra/reactive) 
and [spring-projects/spring-boot](https://github.com/spring-projects/spring-boot/tree/master/spring-boot-samples/spring-boot-sample-data-cassandra)
2. Find out more about Reactor: [reactor/reactor-core](https://github.com/reactor/reactor-core)
3. ScyllaDB: [scylladb/scylla](https://github.com/scylladb/scylla)
