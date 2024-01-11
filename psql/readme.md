# psql - PostgreSQL interactive terminal

Reference: <https://www.postgresql.org/docs/current/app-psql.html>

## Connect to Postgres DB

Start Postgres DB with Docker (optional)

    docker run --publish 5432:5432 --env POSTGRES_PASSWORD=POSTGRES_PASSWORD postgres

Connect with `psql`:

    psql --host HOST --port 5432 --username postgres --dbname postgres

## psql Commands

### Database Commands

List all databases

    \l [pattern]

Connect to database

    \c database_name

### Relation Commands

Describe roles (a.k.a. users or groups)
 
    \du
    \dg

Describe relations (tables, etc.)

    \dt

Describe attributes or relations matching pattern

    \d+ [pattern]

Describe data types

    \dT
