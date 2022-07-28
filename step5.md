<div class="top">

# Querying table "movies"
### [◂](command:katapod.loadPage?step4){.steps} Step 5 of 11 [▸](command:katapod.loadPage?step6){.steps}
</div>

Table `movies` stores information about movies, which are uniquely identified by their titles and release years.
This table has single-row partitions and 
the primary key defined as `PRIMARY KEY ((title, year))`. 
Let's first retrieve all rows from the table to learn how the data looks like and then focus 
on predicates that the primary key can support.

Q1. Retrieve all rows:
<details>
  <summary>Solution</summary>

```
SELECT * FROM movies;
```

</details>

Q2. Retrieve one row/partition:
<details>
  <summary>Solution</summary>

```
SELECT * FROM movies
WHERE title = 'Alice in Wonderland'
  AND year = 2010;
```

</details>

Q3. Retrieve two rows/partitions:
<details>
  <summary>Solution</summary>

```
SELECT * FROM movies
WHERE title = 'Alice in Wonderland'
  AND year IN (2010, 1951);
```

</details>

[continue](command:katapod.loadPage?step6){.orange_bar}