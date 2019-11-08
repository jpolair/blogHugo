---
title: "02 Les Types Complexes"
date: 2019-11-07T22:43:26+01:00
draft: true
---

Pour stocker plusieurs valeurs dans une seule variable ou constante, ce qui peut être pertinent certaines fois, exemple var daysOfTheWeek, il y a les tuples et les collections, les collections sont divisées en plusieurs types....

### les Arrays (tableaux)

{{< highlight swift >}}
var fruits: [String] = ["orange", "apples", "lemon"]
var colors = ["blue", "red", "green"]
print(fruits)
{{< / highlight >}}

- Un tableau commence avec [ et se termine avec ] - shift + option + ( ou ) sur mac
- Les éléments d'un même tableau sont de même type
- On sépare les éléments par une virgule
- les tableaux peuvent être typés par inférence ou en précisant le type de ce qu'il contienne entre crochet 

{{< highlight swift >}}
var names = ["Nathan", "Jean-Paul", "Pauline","Léa"]
var bestOfTheWorld = names[1]
print("The best of the world is..... \(bestOfTheWorld)")
// Décommenter la ligne en dessous retourne une erreur ? 🤥🤔
// print(names[4])
{{< / highlight >}}

- on accède aux éléments d'un tableau comme ceci nomDuTableau[indice élément]
- Le premier indice d'un tableau est 0 !!!
- essayer d'accéder à un indice n'existant pas retournera une erreur.... le programme plante !!!

### Les Set (les ensembles)

- les Set sont commes les Arrays sauf que:
- Ils ne peuvent pas contenir 2 fois la même valeur, 
- si on entre deux fois la même valeur, la seconde valeur sera ignorée
- on ne peut pas accèder à une valeur avec l'index (on y accède gràce à une boucle, on verra cela plus tard...)

{{< highlight swift >}}
let friends = Set(["Fred", "John", "Fred", "John", "Ahmed"])
let oddDigits: Set = [1, 3, 5, 7, 9] // création d'un Set également, Set de Int
// Ne change pas le var suivant en let ?? 😉
var evenDigits = Set<Int>() 
// whaooo... création d'un Set vide au dessus
// toutefois il ne pourra recevoir que des Int par la suite
print("les amis sont \(friends)")
print("evenDigits \(evenDigits)")
// si tu as changé le var en let la ligne suivante va pas aimé....
evenDigits.insert(6)
print("evenDigits \(evenDigits)")
{{< / highlight >}}

### Les Dictionaries (les dictionaires)

- le dictionnaire associe des "clés" d'un même type à des "valeurs" d'un même type
- chaque clé est unique

{{< highlight swift >}}
// Ici je saute des lignes entre les éléments 
// ça ne change rien 
var levels: [String:Int] = [
    "beginer": 1, 
    "confirmed": 2, 
    "expert": 3, 
    "papa": 4, 
    "newbie": 0
    ]
// j'accède aux valeurs comme ceci :
print(levels["beginer"])
// la console m'affiche Optional(1) et pas 1, pourquoi ? 😕
// Optional est un type on y reviendra, cet affichage est normal

// voici comment on ajoute une clé/valeur au dictionaire levels
levels["superStar"] = 12
print(levels)

// on change une valeur de la même manière que pour une création
// si la clé existe déjà la nouvelle valeur sera insérée
levels["papa"] = 12
print(levels)
{{< / highlight >}}

### Les Tuples  (les tuples.... en français 😁)

- Ils permettent de stocker des valeurs, de même type ou pas, relatives à un même élément
- on peut changer les valeurs du tuple mais en gardant les mêmes type
- une fois définit, on n'ajoute pas de valeur à un Tuple 

{{< highlight swift >}}
var person = (firstname: "Jean", lastname: "Air", address: "9 allée des roses", cool: true)
// je change la valeur du 1er élément (indice 0)
person.0 = "Paul"
print(person)
// Décommenter la ligne suivante crée un erreur 
// person.2 = 6 // type initial de address(indice 2) est String
// en dessous je change la valeur grâce à la notation point
person.address = "6 allée des cerisiers"
print(person)
{{< / highlight >}}

### Les Enums (les enumérations)

- les enums servent à créer des variables plus "sécurisées"
- les enums évitent les erreurs de "Typo"

{{< highlight swift >}}
// Pour déclarer un enum, pas de let ou de var
// un enum n'est pas une variable ou une constante, c'est un enum
// le nom de l'enum commence avec une majuscule (par convention)
// Cet Enum teste l'état de la connection au réseau en cours
enum Status {
    case connecting
    case connected
    case disconected
    case disconecting
}
// c'est plus pertinent que 4 booléens, ou 4 String
// l'utilisateur est soit connecté, soit déconnecté, 
// soit en cours de connection, soit en cours de déconnection

// Ici c'est lisible, clair, l'utilisateur et connecté 
var status = Status.connected

// le risque sans enum c'est ça:
var connectionStatus = "connected"
// et plus loin dans le programme
connectionStatus = "connect"
// et plus loin
connectionStatus = "Ok"
// l'enum est là pour limiter le nombre de cas 
// De plus les Ide comme Xcode proposeront l'auto-complétion


{{< / highlight >}}


*****************************

### Tips

{{< highlight swift >}}
// Swift nous mets à dispostion des outils pour travailler sur ces
// éléments, ces outils sont des méthodes ou des propriétés
// on verra la notion de méthode et de propriété plus tard, mais 
// voici déjà quelques "outils" intéressant...

var family = ["Pauline", "Stéphanie", "Nathan", "Léa", "Jean-Paul"]
// pour connaitre la taille de family j'utilise la propriété count
print("la famille est composée de \(family.count)")

// j'ajoute un élément à la fin du tableau
family.append("Iron le chien")
print(family)

// je vérifie si le tableau est vide avec la propiété isEmpty
print(family.isEmpty) // false
// j'affecte un tableau vide à family, possible car family a déjà
// été déclaré, attention, bien que family soit vide son type reste [String]  
family = []
print(family.isEmpty) // true

// Pour vérifier le type d'une variable, on utilise la méthode type
print(type(of: family)) // Array<String> qui est l'équivalent de [String]

// Pour créer un Array vide, ou un set vide
var numbers = [Int]()
var otherNumbers = Set<Int>()

// 1 - je déclare un tableau de String
var countries = ["France", "Etats-Unis", "Niger", "Chine", "Jamaique"]
// 2 - j'itère dans mon tableau (je parcours ses éléments) gràce à une boucle for
// la boucle for existe dans tous les languages, 
// elle s'écrit toujours "à peu près" comme ici... à peu près 😉 
for country in countries {
    print(country)
}

{{< / highlight >}}
