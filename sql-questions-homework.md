# SQL Homework

For this homework, we will use sqlite3, it is already available on your machine using the command `sqlite3`, copy the file sql_dump.sql in a folder where your sqlite3 database will be, then type:

```
sqlite3 wishlists.db < sql_dump.sql
```

This will create the database wishlists. Unlike Postgres, sqlite3 create a file in the folder where you are, if you delete this file, you delete the db !

To connect to the database, type `sqlite3 wishlists.db`, then you can execute sql statements.

Write SQL statements that:

    1. Selects the names of all products that are not on sale.
SELECT "name" FROM products WHERE on_sale = 'f';
    2. Selects the names of all products that cost less than £20.
SELECT "name" FROM products WHERE "price" < 20;
    3. Selects the name and price of the most expensive product.
SELECT "name", "price", max("price") FROM products;
    4. Selects the name and price of the second most expensive product.
SELECT "name", "price", max("price") FROM products WHERE "price" NOT IN (SELECT MAX ("price") FROM products);
    5. Selects the name and price of the least expensive product.
SELECT "name", "price", MIN("price") FROM products;
    6. Selects the names and prices of all products, ordered by price in descending order.
SELECT "name", "price" FROM products ORDER BY "price" DESC;
    7. Selects the average price of all products.
SELECT AVG("price") FROM products;
    8. Selects the sum of the price of all products.
SELECT SUM("price") FROM products;
    9. Selects the sum of the price of all products whose prices is less than £20.
SELECT SUM("price") FROM products WHERE "price" < 20;
    10. Selects the id of the user with your name.
SELECT "id" FROM users WHERE "name" = 'Jon Rogers';
    11. Selects the names of all users whose names start with the letter "J".
SELECT "name" FROM users WHERE "name" LIKE 'J%';
    12. Selects the number of users whose first names are "Spencer".
SELECT COUNT("name") FROM users WHERE "name" = "name" LIKE 'Spencer%';
    13. Selects the number of users who want a "Teddy Bear".
SELECT COUNT("id") FROM wishlists WHERE "product_id" = 1;
    14. Selects the count of items on the wishlish of the user with your name.
SELECT COUNT("name") FROM users JOIN wishlists ON users."id", wishlists."user_id" WHERE users."id" = 'Jon Rogers';
    15. Selects the count and name of all products on the wishlist, ordered by count in descending order.
    16. Selects the count and name of all products that are not on sale on the wishlist, ordered by count in descending order.
    17. Inserts a user with the name "Jonathan Anderson" into the users table. Ensure the created_at column is set to the current time.
INSERT INTO users ("created_at", "name") VALUES (CURRENT_TIMESTAMP , "Jonathan Anderson");
    18. Selects the id of the user with the name "Jonathan Anderson"?
SELECT "id" FROM users WHERE "name" = "Jonathan Anderson";
    19. Inserts a wishlist entry for the user with the name "Jonathan Anderson" for the product "The Ruby Programming Language".
    20. Updates the name of the "Jonathan Anderson" user to be "Jon Anderson".
    21. Deletes the user with the name "Jon Anderson".
    22. Deletes the wishlist item for the user you just deleted.

Please supply SQL statements, and the results they generate.



###Hints
  - As with anything, if you get stuck, move on, then go back if you have time.
  - Don't spend all night on it!
  - Use the resources on teh internetz to solve harder ones - there are solutions to these questions that work with what we've learnt today, but other tools exist in SQL that could make the queries 'better' or 'easier'.
