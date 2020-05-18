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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzOTUyNjk5MCw2MzAzOTA3NDNdfQ==
-->