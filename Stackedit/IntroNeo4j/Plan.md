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
MATCH (p1:Person)-[rel:HELPED]->(p2:Person)
WHERE p1.name = 'Tom Hanks' AND p2.name = 'Gary Sinise'
SET rel.research = 'war history' amd rel.otraproiedad=15
`MATCH (p1:Person)-[rel:HELPED]->(p2:Person)
WHERE p1.name = 'Tom Hanks' AND p2.name = 'Gary Sinise'
SET rel.research = 'war history'
```

# hasta aqui esta lo necesario para las cryptos con relacion de 'valer' con propiedades de unidad en que se mide y 'valor' podemos crear otra relacion para otro tipo de cambio 

### mejores practicas

```sql
MERGE (variable:Label{nodeProperties})
RETURN variable // nodos

MERGE (variable:Label {nodeProperties})-[:REL_TYPE]->(otherNode)
RETURN variable //relaciones

```


para automatizar mejor el poblado de la base usar parametros 

```sql
:param actorName => 'Tom Hanks'

MERGE(m:MovieFoo { title: 'foo2'}) //mi ejemplo de creacion de nodos
```

## indices 

```sql
CREATE INDEX ON :Movie(released)
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMDQ5ODE3NzAsLTcwMzE4MjMzOCwtMT
M5Mzg0MTM1Myw0MjU5Njc0OTIsMzMxMzE5ODcxLDEzNzI1MDEx
NDEsLTEzOTUyNjk5MCw2MzAzOTA3NDNdfQ==
-->