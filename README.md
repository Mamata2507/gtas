for instalation using docker compose(after installing docker compose)
run the following command:
docker-compose -f elk-docker-compose.yml -f neo4j-etl-docker-compose.yml -f docker-compose.yml -f local-deployment.yml pull
(this pull all the docker images you need for this)
docker-compose -f elk-docker-compose.yml -f neo4j-etl-docker-compose.yml -f docker-compose.yml -f local-deployment.yml -d up
(this install the app)

