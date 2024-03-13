150220241420
Status: #idea #Fleeting 
Tags: #Sql  #BancoDeDados 
# Consultas úteis
### Consulta feita para pegar um padrão na primeira parte de uma string :
```
SELECT DISTINCT CITY FROM STATION WHERE LEFT(CITY,1) = 'A' OR LEFT(CITY,1) = 'E' OR LEFT(CITY,1) = 'I' OR LEFT(CITY,1) = 'O' OR LEFT(CITY,1) = 'U';
```
```
SELECT DISTINCT CITY
FROM STATION
WHERE LEFT(CITY, 1)  IN ('a','e','i','o','u');
```



*
## References
*
