# for instalation using docker compose(after installing docker compose)

**run the following command:**

```[root@vahid gtas]# docker-compose -f elk-docker-compose.yml -f neo4j-etl-docker-compose.yml -f docker-compose.yml -f local-deployment.yml pull```

(this pull all the docker images you need for this)

```[root@vahid gtas]# docker-compose -f elk-docker-compose.yml -f neo4j-etl-docker-compose.yml -f docker-compose.yml -f local-deployment.yml -d up```

(this install the app)

**result should be like this:**
```

[root@vahid gtas]# docker ps -a
CONTAINER ID        IMAGE                          COMMAND                  CREATED             STATUS              PORTS                                                      NAMES
7a3bc9dc41fc        wcogtas/neo4j-etl-job:1.0.0    "/bin/sh -c 'export …"   7 days ago          Up 47 hours                                                                    etl-job

ba6987f2b903        wcogtas/logstash:1.0.0         "dockerize -wait fil…"   7 days ago          Up 47 hours         5044/tcp, 9600/tcp                                         logstash

36a52159df64        wcogtas/kibana:1.0.0           "dockerize -wait fil…"   7 days ago          Up 47 hours         0.0.0.0:5601->5601/tcp                                     kibana

a3cef9735002        wcogtas/gtas-scheduler:1.0.0   "/bin/sh -c 'mkdir -…"   7 days ago          Up 47 hours         8080/tcp                                                   gtas-scheduler

89b947295923        wcogtas/neo4j:1.0.0            "/sbin/tini -g -- /d…"   7 days ago          Up 47 hours         0.0.0.0:7474->7474/tcp, 7473/tcp, 0.0.0.0:7687->7687/tcp   neo4j

21628826120c        wcogtas/http-proxy:1.0.0       "/bin/sh -c 'credent…"   7 days ago          Up 47 hours         0.0.0.0:80->80/tcp, 0.0.0.0:443->443/tcp                   http-proxy

8069bb74608c        wcogtas/mariadb:1.0.0          "docker-entrypoint.s…"   7 days ago          Up 47 hours         0.0.0.0:3306->3306/tcp                                     mariadb

6ff0de937945        wcogtas/elk-setup:1.0.0        "/bin/sh -c 'echo y …"   7 days ago          Up 47 hours         5044/tcp, 9600/tcp                                         elk-setup

850e1d28ccd7        wcogtas/elasticsearch:1.0.0    "dockerize -wait fil…"   7 days ago          Up 2 seconds        0.0.0.0:9200->9200/tcp, 0.0.0.0:9300->9300/tcp             elasticsearch

76b4fe4f3a17        rmohr/activemq:5.15.9          "/bin/sh -c 'bin/act…"   7 days ago          Up 47 hours         1883/tcp, 5672/tcp, 8161/tcp, 61613-61614/tcp, 61616/tcp   activemq

311ad198d809        wcogtas/web-app:1.0.0          "/bin/sh -c 'mkdir -…"   7 days ago          Up 47 hours         0.0.0.0:8080->8080/tcp, 0.0.0.0:8443->8443/tcp             web-app
```
