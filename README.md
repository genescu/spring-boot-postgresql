# spring-boot-postgresql

docker pull postgres

mkdir -p $HOME/docker/volumes/postgres

docker run --rm   --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data  postgres

http://localhost:8090/h2-console/


# Database
spring.datasource.url=jdbc:postgresql://localhost:5432/postgres

spring.datasource.username=postgres

spring.datasource.password=docker


# Action

#2. Upload CSV file http://localhost:8090/upload

#3. Retrieve some data


http://localhost:8090/ships/1

curl -X GET "http://localhost:8090/ships/1"


A.
/port/{id}/{dateTime}

http://localhost:8090/port/2/1.1.2016%2012:00

http://localhost:8090/port/2/04.01.2016%2012:00

curl -X GET "http://localhost:8090/port/2/1.1.2016%2012:00"

curl -X GET "http://localhost:8090/port/2/04.01.2016%2012:00"
        

B.

/port/{id}/{startTime}/{endTime}

http://localhost:8090/port/2/1.1.2016%2012:00/04.01.2017%2020:55:23

curl -X GET "http://localhost:8090/port/2/1.1.2016%2012:00/04.01.2017%2020:55:23"



