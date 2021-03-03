Module that test whether we can setup a REST API using ORM Panache and a datasource with XA transactions using a MySQL database.

Base application:
- Define multiple datasources (https://quarkus.io/guides/datasource#multiple-datasources): default (transactions enabled), `with-xa` (transactions xa).
- Define Panache entity `ApplicationEntity` and its respective REST resource `ApplicationResource` (https://quarkus.io/guides/rest-data-panache).
- Define a REST resource `DataSourceResource` that provides info about the datasources.

Tests:
- Mock datasources using Testcontainers.
- Test CRUD operations on `ApplicationEntity` using default datasource.
- Test whether the `DataSourceResource` returns proper configuration for each datasource.