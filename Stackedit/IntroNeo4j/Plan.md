Primero crear nodos:
	- Etiquetas dobles
	- CurrencyBitcoin, CurrencyDLL, CurrencyPesosMx
Luego relaciones


Ejemplo 

 ```sql
 MATCH (a:Person), (m:Movie), (p:Person)
WHERE a.name = 'Liam Neeson' AND
      m.title = 'Batman Begins' AND
      p.name = 'Benjamin Melniker'
CREATE (a)-[:ACTED_IN]->(m)<-[:PRODUCED]-(p)
RETURN a, m, p
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc1NDAxMjMwMiw2MzAzOTA3NDNdfQ==
-->