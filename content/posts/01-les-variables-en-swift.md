---
title: "01 Les Variables en Swift"
date: 2019-11-07T21:55:57+01:00
draft: false
---

Les variables servent à stocker des informations.
En swift une variable a un type et elle le garde

Il y a deux notions différentes pour le stockage de valeurs :
- les variables, elles peuvent changer de valeurs elles se déclarent avec le mot clé: var
- les constantes, elles ne peuvent pas changer de valeurs elles se déclarent avec le mot clé: let

### Le type String (texte)

{{< highlight swift >}}
var fruit: String = "orange"
print(fruit)
{{< / highlight >}}

Ici j'ai déclaré une variable de type String, en précisant sont type explicitement:
- j'écris var
- je nomme ma variable avec un nom pertinant ici c'est fruit
- je mets deux points suivi du type String 
- je mets un égal et la valeur de ma variable entourée de guillemets double
- l'instruction print sert à afficher la valeur de ma variable dans une console

{{< highlight swift >}}
var day: String
day = "Friday"
print(day)
{{< / highlight >}}

Ici c'est un peu différent:
- je déclare une variable day de type String sans lui donner de valeur  
- je donne une valeur à la variable day (il n'y pas le mot clé var car la variable est déjà déclarée)
- l'instruction print sert à afficher la valeur de ma variable dans une console

{{< highlight swift >}}
// La méthode cool.... 
let firstname = "Jean-Paul"
// firstname = "Allan" ceci génère une erreur (si on enlève les //)
print(firstname)
{{< / highlight >}}

Cette fois je déclare une constante avec le mot clé let, ce qui veut dire que je ne peux pas changer la valeur de firstname

Je ne précise pas de type, Swift est capable de typer par inférence, en fait il devine que la variable est bien un String grâce à la valeur que l'on a fournit, ici une valeur entre deux guillemets 😃

J'ai commencé deux lignes avec // ces lignes sont des lignes de commentaires... heureusement sinon il y aurait deux erreurs en copiant collant dans onlineswift :
- première erreur car La méthode cool ne correspond à rien en swift
- deuxième erreur car on tente de réaffecter une constante.... et c'est impossible !!! 

### Les types Int, Float, Double (les nombres)

{{< highlight swift >}}
var applesQuantity = 6
var orangesQuantity: Int = 6
var fruitsQuantity = apples + oranges
print("En tout j'ai \(fruitsQuantity) fruits")
{{< / highlight >}}

Ici je déclare deux variable de type Int (Integer, Entier), une par inférence, une explicitement, puis j'additionne ces deux variables (oui les opérations de bases sont disponibles en Swift)

Ici je peux additionner car les deux nombres sont de même type, le type Integer

la dernière ligne est un peu différente:
- je me sert de l'instruction print pour afficher
- dans les parenthèses j'ai des guillemets au début et à la fin 🤔
- entre ces guillemets j'ai du texte.... normal... et la variable fruitsQuantity comme ça \\(fruitsQuantity)

cette notation, au dessus, s'appelle string interpolation, elle permet de mettre dans une string une variable ou une constante, c'est quand même mieux d'afficher la variable avec un peu de texte autour... cette fois on sait de quoi on parle

{{< highlight swift >}}
let temperatureToday: Float = 22.5
let temperatureYesterday = 19.0
// décommente la ligne suivante pour avoir une belle erreur
// let difference = temperatureYesterday - temperatureToday
{{< / highlight >}}

Le problème, ici, c'est que le type n'est pas le même, par défaut (en typage par inférence) les nombres décimaux sont de type Double... et temperatureToday est de type Float, en swift les opérations ne sont possibles que pour les valeurs de même type !!!

Il faut donc, ou, passer temperatureToday en Double (par inférence ou explicitement), ou passer temperatureYesterday en Float explicitement car par défaut ce sera un Double

ℹ️ La différence entre Float et Double ??? 🤔Un Float c'est 7 chiffres après la virgule, un Double c'est le double 😮

### Le type Bool (boolean)

{{< highlight swift >}}
let isSad = false
let isCool = true
var isAuthorized: Bool = true 
{{< / highlight >}}

une variable de type Bool peut avoir deux états: true ou false, ces variables sont utilisées dans tous les languages informatique, pour comparer dans les conditions, pour définir un état... etc on verra ça un peu plus tard...

Quelques exemples d'usage de booléen en programmation: Quizz avec vrai ou faux, application loguer ou non, button clickable ou non, etc...

********************

### Tips

{{< highlight swift >}}
// il faut le même nombre d'espace avant et après le signe égal sinon Erreur
var goodSpace="Ici"
var goodSpace = "Ici aussi"
var badSpace= "Distance pas pareil avant et après le signe espace c'est pas bon"

// On peut concatener les String
var firstname = "James"
var lastname = "Bond"
var name = firstname + lastname
print(name) // Affichera JamesBond
var nameCorrect = firstname + " " + lastname
print(nameCorrect) // Affichera James Bond
print("\(firstname) \(lastname)") // Affichera James Bond

// on peut nommer les variable et le constantes comme on veut, toutefois:
// la langue c'est l'anglais, c'est plus cohérent par rapport aux mots clés
// les booleens c'est souvent is.... est-il admin ? oui(true) ou non(false) 

let isAdmin = true

// on opte pour le camelCase en swift c-à-d première lettre en minuscule
// et tout les mots qui suivent on met la première lettre en majuscule
let isSuperAdminOfTheWorld = false
{{< / highlight >}}

