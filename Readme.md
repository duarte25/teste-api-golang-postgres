## Comandos para Postgres em Docker e criação do user, banco e table

* docker run -d --name api-todo -p 5435:5432 -e POSTGRES_PASSWORD=1234 postgres:13.5 

* docker exec -it api-todo psql -U postgres

* create database api_todo;

* create user user_todo;

* alter user user_todo with encrypted password '1122';

* grant all privileges on database api_todo to user_todo;

* \c api_todo;

* create table todos (id serial primary key, title varchar, description text, done bool default FALSE);

* grant all privileges on all sequences in schema public to user_todo;

* grant all privileges on all tables in schema public to user_todo;