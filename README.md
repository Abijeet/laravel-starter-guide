# laravel-starter-guide
A guide on handling a medium scale project using Laravel.

# Database design
So the first thing we will do is design our database. This can be done by using a tool like [MySQL Workbench](https://www.mysql.com/products/workbench/) which will also allow you to then export it to a SQL file with which you can build a database.

We will take the SQL file, and generate a single migration file for the initial database design. This can be done as follows, as described in the StackOverflow post [here](https://stackoverflow.com/a/23983792/903324).

```sql
DB::unprepared(file_get_contents('full/path/to/dump.sql'));
```

While designing the database try to account for the entities in your project and the relationship between them. You should also think of the different user roles in your application and how they will be accessing the various entities.

## Things to note
1. Follow proper naming conventions based on Laravel guidelines as mentioned [here](https://laravel.com/docs/5.6/eloquent#introduction).
2. Ensure proper indexes (primary keys, foreign key and indexes) are created based on how you intend to access the data and  the amount of data you expect the table to have.
3. Although the initial database design will be done using a single migration, future modifications will be carried out using [Laravel migrations](https://laravel.com/docs/5.6/migrations).

