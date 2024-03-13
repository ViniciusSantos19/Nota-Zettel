160220241157
Status: #idea
Tags: 
# Queries ùteis2 em sql
Essa querie faz o uso de funções bastante úteis no sql. como sqrt, que seria para tirar a raiz, power, que seria para elevar a uma potência e round que seria para arredondar um número.
```
SELECT ROUND(SQRT(POWER(MAX(LAT_N) - MIN(LAT_N), 2) + POWER(MAX(LONG_W) - MIN(LONG_W), 2)), 4) AS Euclidean_Distance
FROM STATION;

```
If também pode ser usado em  queries de sql:
```
SELECT N, IF(P IS NULL,"Root",IF((SELECT COUNT(*) 
FROM BST 
WHERE P=B.N)>0,"Inner","Leaf")) FROM BST AS B 
ORDER BY N;
```


*
## References
*
