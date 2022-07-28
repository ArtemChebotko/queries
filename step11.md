<div class="top">

# Setting limits
### [◂](command:katapod.loadPage?step10){.steps} Step 11 of 11 [▸](command:katapod.loadPage?finish){.steps}
</div>

Finally, a query can limit the number of rows that can be returned.
This is doable with clauses `PER PARTITION LIMIT` and `LIMIT`, which can be used by themselves 
or together in the same query. 

Q1. Use no limits:
```
SELECT * FROM ratings_by_user
WHERE email IN ('joe@datastax.com',
                'jim@datastax.com');
```

Q2. Use the per partition limit:
```
SELECT * FROM ratings_by_user
WHERE email IN ('joe@datastax.com',
                'jim@datastax.com')
PER PARTITION LIMIT 2;
```

Q3. Use the overall limit:
```
SELECT * FROM ratings_by_user
WHERE email IN ('joe@datastax.com',
                'jim@datastax.com')
LIMIT 3;
```

Q4. Use both limits:
```
SELECT * FROM ratings_by_user
WHERE email IN ('joe@datastax.com',
                'jim@datastax.com')
PER PARTITION LIMIT 2
LIMIT 3;
```

[continue](command:katapod.loadPage?finish){.orange_bar}
