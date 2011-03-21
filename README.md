# Mysql to PostgreSQL

This is a ruby script which migrates data from a MySQL database to PostgreSQL. It can be run as a
one off migration, or as a delta script to copy newly modified data.

## Prerequisites

* Designed to work on a Rails 2.x application
* Majority of tables should have:
  * primary key column (usually called id, but can be changed)
  * updated_at column
  * index on updated_at

## Steps

* Edit mysql_to_postgresql
  * Put in database credentials
  * Add any tables without an updated_at to TABLES_WITHOUT_UPDATED_AT
* Update database.yml in your application to point to PostgreSQL
* Create database tables by running: `rake db:create db:migrate`
* Run ./mysql_to_postgresql

## License

See the LICENSE file.
