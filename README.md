docker run --name example-db -p 5431:5432 -e POSTGRES_PASSWORD=pass -d postgres:12.2
psql -h localhost -p 5431 -U postgres -c "create user example_user with password 'pass';"
psql -h localhost -p 5431 -U postgres -c "create database exampledb;"
psql -h localhost -p 5431 -U postgres -c "grant all privileges on database exampledb to example_user;"
