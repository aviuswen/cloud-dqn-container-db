# Testing for Docker Containerization of databases and admin tools

### Docker-compose cmds:
docker-compose up
*Brings up 2 containers: One instance of Postgres and adminer*

docker-compose stop
docker-compose rm 
docker-compose rm -f
docker-compose ps

#### Adminer Access/Login
System: Postgres
Server: pgdb 		// docker-compose sets up the network and this is available
Username: root 		// docker-compose.yml::POSTGRES_USER
Password: password 	// docker-compose.yml::POSTGRES_PASSWORD
Database: blogapp	// docker-compose.yml::POSTGRES_DB

### To connect to DB via psql (you must open the port)
$ psql -U root -W blogapp -h 127.0.0.1 -p 5432

### Run psql from inside of server
$ docker-compose exec pgdb psql -U root -W blogapp

list Tables
blogapp=# \d+   

exit
blogapp=# \q
