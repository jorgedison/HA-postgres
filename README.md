# High Scalability Postgres With Docker

Files to deploy postgres databases in high availability using docker swarm.

The complete stack is:
- docker swarm mode (orchestration)
- haproxy (endpoint for db write/reads)
- etcd (configuration, leader election)
- patroni (governs db repliation and high availability)
- postgres

## Deploying the stack

```sh
$ docker swarm init
```
```sh
$ docker stack deploy -c docker-stack.yml pg-cluster
```
## Validating the stack

```sh
$ docker swarm ls
```
```sh
$ docker services ls
```

[![N|Solid](https://usuarioperu.com/wp-content/uploads/2019/04/HA-postgres.png)](https://usuarioperu.com/wp-content/uploads/2019/04/HA-postgres.png)

The master db is accessible on localhost:5000 and the replicas on 5001

[![N|Solid](http://usuarioperu.com/wp-content/uploads/2019/04/HA-postgres-validation.png)](http://usuarioperu.com/wp-content/uploads/2019/04/HA-postgres-validation.png)
