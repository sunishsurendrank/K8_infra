Installing cassandra in kubernetes as pod

We can install the cassandra using the cassandra.yaml.

To Test cassandra is working 

```
kubectl run -it client --image cassandra -- /bin/bash

```

After entering to the client pod run the below command

```
export CQLSH_HOST=cassandra
```

The run the cqlsh command

To create namespace

```
create keyspace events_keyspace with replication = {'class':'SimpleStrategy','replication_factor':2};
```

```
CREATE TABLE IF NOT EXISTS events_keyspace.test (name text ,place text,PRIMARY KEY (name));
```

```
INSERT INTO events_keyspace.test (name,place) VALUES ('sunish','thrissur');
```

```
select * from events_keyspace.test
```