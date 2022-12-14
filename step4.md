<div class="top">

# Querying table "users"
### [◂](command:katapod.loadPage?step3){.steps} Step 4 of 11 [▸](command:katapod.loadPage?step5){.steps}
</div>

Table `users` stores information about users who are uniquely identified by their email addresses.
This table has single-row partitions and 
the primary key defined as `PRIMARY KEY ((email))`. 
Let's first retrieve all rows from the table to learn how the data looks like and then focus 
on predicates that the primary key can support.

Q1. Retrieve all rows:
```
SELECT * FROM users;
```

Q2. Retrieve one row/partition:
```
SELECT * FROM users
WHERE email = 'joe@datastax.com';
```

Q3. Retrieve two rows/partitions:
```
SELECT * FROM users
WHERE email IN ('joe@datastax.com',
                'jen@datastax.com');
```

[continue](command:katapod.loadPage?step5){.orange_bar}