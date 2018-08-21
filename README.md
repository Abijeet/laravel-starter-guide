# Laravel Starter Guide
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
4. Based on the type of languages you need to support, choose the database collation wisely. Read [here](https://stackoverflow.com/questions/367711/what-is-the-best-collation-to-use-for-mysql-with-php) for more instructions with respect to MySQL.

# Install Laravel
I'll not go into too much depth on how to do this. Follow the instructions [here](https://laravel.com/docs/5.6/installation) and you should be good to go.

# Project checklist
At this point, before starting the project further, I highly recommend filling out a checklist. Some of the questions on this might include,

1. How much traffic do we expect the application to draw?
2. Do we need to support multiple languages?
3. Does the application require any heavy computations? Can these be offloaded and done at offpeak hours or will this have to be done on the fly?
4. What sort of notifications systems will we have to support - Emails, SMS, Voice call etc?
5. Will I need a REST API now or in the future to handle mobile devices? Is this a single page application?

Those are a general set of questions that I came up with, but you'll probably have more based on the type of project that you are handling. It is good to be able to answer them now so you know what the scope of your project is, what plugins and third party services you'll need to integrate with.



