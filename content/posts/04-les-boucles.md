---
title: "04 Les Boucles"
date: 2019-11-08T22:37:36+01:00
draft: true
---

Les boucles un sujet important dans les languages informatique, on en a déjà brièvement parlé on va approfondir le sujet

### La boucle for 

La boucle for est très utilisée, elle est très puissante, elle permet beaucoup de chose

{{< highlight swift >}}
var values = [4, 12, 22, 34]
// pour chaque élément de values, 
// je crée une variable temporaire que je nomme value
// je multiplie chaque élément par 2
for value in values {
    value * 2
}
print(values) // values n'a pas changé... et c'est normal !!!
{{< / highlight >}}

Dans l'exemple précédent values n'a pas été modifié car j'itère dans les éléménts du tableau, je modifie la valeur de la variable temporaire et jamais je ne change le tableau lui même 

{{< highlight swift >}}
var values = [4, 12, 22, 34]
// je crée un tableau vide d'entiers 
var results = [Int]()
for value in values {
// j'ajoute grâce à la méthode append les éléménts dans le tableau vide    
    results.append(value * 2)
}
print(results)
{{< / highlight >}}

dans l'exemple précédent j'ai créé mon tableau vide hors de la boucle et je l'affiche une fois qu'il est complet grace à print hors de la boucle  