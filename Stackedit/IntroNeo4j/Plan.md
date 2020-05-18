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


-   Add a  _uniqueness constraint_  that ensures that a value for a property is unique for all nodes of that type.
-   Add an  _existence constraint_  that ensures that when a node or relationship is created or modified, it must have certain properties set.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NjUwMjIyMiwtMTAwNDk4MTc3MCwtNz
AzMTgyMzM4LC0xMzkzODQxMzUzLDQyNTk2NzQ5MiwzMzEzMTk4
NzEsMTM3MjUwMTE0MSwtMTM5NTI2OTkwLDYzMDM5MDc0M119
-->