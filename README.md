# XPath
1) Quel est la population de l'Africe.
```
sum(//country[encompassed[@continent='africa']]/population[last()])
````
2) Combien de pays a-t-on en Afrique
```
count(/*/country/encompassed[@continent='africa'])
```
3) Quel sont les pays traversés par Amazonas 
```
//river[name='Amazonas']/@country
```
4) Quel sont les pays qui bordent l'océan Atlantique
```
//sea[name="Atlantic Ocean"]/@country
```
5) Combien de Musulmans en Europe
```
sum(//country[encompassed/@continent='europe']/(religion[.='Muslim']/@percentage  div 100 * population[last()] * encompassed[@continent='europe']/@percentage  div 100))
```
6) Combien et quels sontles pays qui est à plus d'un continent
```
count(//country[count(encompassed)>1])
```
7) Quels sont les pays limitrophes de l'allemagne
```
//country(border/@country='D']/name
```

8) Quel est le pays ou population est la plus dense ?
```
//country[(population[last()] div @area)=max(//country/(population[last()] div @area ))]/name
```
