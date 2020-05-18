Primero crear nodos:
	- Etiquetas dobles
	- CurrencyBitcoin, CurrencyDLL, CurrencyPesosMx
Luego relaciones


Ejemplo 

 ```sql
MATCH (a:Person), (m:Movie)
WHERE a.name = 'Christian Bale' AND m.title = 'Batman Begins'
CREATE (a)-[rel:ACTED_IN]->(m)
SET rel.roles = ['Bruce Wayne','Batman']
RETURN a, m
```

__When you create relationships based upon a `MATCH` clause, you must be certain that only a single node is returned for the `MATCH`, otherwise multiple relationships will be created.__

# Crear sin return 
```sql 
MATCH (m:Movie)
WHERE m.title = 'Forrest Gump'
MATCH (p:Person)
WHERE p.name = 'Tom Hanks' OR p.name = 'Robin Wright' OR p.name = 'Gary Sinise'
CREATE (p)-[:ACTED_IN]->(m)
```
### Add properties to relationships 

```sql
MATCH (p:Person)-[rel:ACTED_IN]->(m:Movie)
WHERE m.title = 'Forrest Gump'
SET rel.roles =
CASE p.name
  WHEN 'Tom Hanks' THEN ['Forrest Gump']
  WHEN 'Robin Wright' THEN ['Jenny Curran']
  WHEN 'Gary Sinise' THEN ['Lieutenant Dan Taylor']
END
````

# hasta aqui esta lo necesario para las cryptos con relacion de 'valer' con propiedades de unidad en que se mide y 'valor' podemos crear otra relacion para otro tipo de cambio 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc0MDE5MjY3MSwtMTM5NTI2OTkwLDYzMD
M5MDc0M119
-->