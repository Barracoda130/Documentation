Just like your table but derived from your base table??? Shit explanation... :(

## Create view
```sqlite
CREATE VIEW vBranch AS 
SELECT branchNo FROM Branch;
```
Try selecting a branch:
`SELECT * FROM vBranch` something will happen