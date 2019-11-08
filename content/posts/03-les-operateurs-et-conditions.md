---
title: "03 Les Operateurs Et Conditions"
date: 2019-11-07T22:44:04+01:00
draft: false
---

En swift on peut se servir des opérateurs arithmétique classique pour caclucler et plus encore...
Il y le (+) pour l'addition, le (-) pour la soustraction, le (/) pour la division, le (*) pour la multiplication et le modulo (%), le modulo retourne le reste de la divison euclidienne 9 % 5 = 4 (car quand on divise 9 par 5 on a un résulat de 1 avec un reste de 5).Le modulo peut-être utilisé pour trouver les nombres pairs/impairs... un nombre pair modulo 2 sera égal à 0 !!! 

### L'addition, et plus encore

{{< highlight swift >}}
// On peut "additionner" les tableaux 😯
var fruits = ["orange", "apples", "lemon"]
var anotherFruits = ["strawberry", "raspberry"]
var allFruits = fruits + anotherFruits
print(anotherFruits)

// On peut concatener les String simplement
var hello = "Hello "
hello += "world !!" // équivaut à hello = hello + "world !!"

// On peut additioner bien sûr, mais attention au type !!!
var addition = 43 + 5 // ok
var badSum = 43 + 5.0 // pas bien !!!
{{< / highlight >}}

### Les conditions.... if 

Les comparaisons et les conditions sont étroitement liées, on compare deux valeurs (ou plus) et on agit fonction du résultat de le la comparaison, c'est à ce moment que nos booléens (Bool) rentrent en action... si (a + b) < 8 alors fait ça..., cette "expression" sera forcément true ou false

{{< highlight swift >}}
// je déclare name
var name = "Jean-Paul"
// je compare name à la valeur Jean-Paul
// je mets == pour comparer, un égal c'est pour affecter !!!
// si le résultat de ma comparaison est true, j'execute le code entre accolades
// si ce false je n'execute pas le code qui se trouvent entre accolades
if name == "Jean-Paul" { 
    print("Trop cool le gars...")
}
{{< / highlight >}}

Dans l'exemple précèdent si le nom n'est pas Jean-paul on ne fait rien mais On peut également prévoir: si ceci fait cela sinon fait ça...

{{< highlight swift >}}
// je déclare deux tuples
var movie = (title: "Matrix", requiredAge: 12)
var person = (name: "Nathan", age: 10)

// je compare l'age exigé pour le film avec l'age de la personne
if movie.requiredAge > person.age {
    print("Il n'est pas possible pour \(person.name) de voir \(movie.title)")
} else {
print("\(person.name) peut voir \(movie.title)")
}
{{< / highlight >}}

C'est cool mais on peut faire encore mieux, car certaines fois il y a plus de deux cas possibles... si ça fait ça, sinon si ça fait ça, sinon si çà..... sinon !!😅

{{< highlight swift >}}
var myNumber = 50

// je mets 2 conditions sur la même ligne grâce à &&
// les deux doivent être vraies pour executer le code entre accolades
if myNumber % 5 == 0 && myNumber % 2 == 0 {
    print("le nombre \(myNumber) est divisible par 2 et par 5")
} else if myNumber % 5 == 0 {
    print("le nombre \(myNumber) est divisible par 5")
} else if myNumber % 2 == 0 {
    print("le nombre \(myNumber) est divisible par 2")
} else {
    print("\(myNumber) n'est pas divisible par 2 ou par 5")
}
// Un nombre % 5(on dit  modulo pas pourcent) étant égal à 0 ça veut dire:
// 50 / 5 = 10 et il reste 0 (c'est ce 0 le résultat du modulo) 51, il reste 1
// Notez que j'ai mis la condition la plus restrictive en premier !!!
{{< / highlight >}}

bien sympa tout ça mais quand il y a plein de sinon si, c'est un peut lourd à lire... quand j'ai plus de trois cas je préfère cas 1 fais ça, cas 2 fais ça, etc...

{{< highlight swift >}}
var language = "swift"

// je switch entre les différents cas
// je dois prévoir un case default
switch language {
    case "python":
        print("cool un peu vieillissant")
    case "javascript":
        print("peux tout faire mais fais attention à ce que tu fais")
    case "PHP":
        print("le language de wordpress...")
    case "swift":
        print("lisible robuste typé 😃")
    default:
        print("connais pas je juge pas..")
}
{{< / highlight >}}

-----------------------------------------

### Tips

{{< highlight swift >}}
// les différents opératueurs
var num1 = 1
var num2 = 2
var isAdmin = true

// le OU impose une des deux conditions vraie
if num 1 > num 2 || isAdmin {
    print("une des deux conditions ok, donc ok")
}
// le ET impose que les deux conditions soient vraies
if num 1 > num 2 && isAdmin {
    print("Deux conditions pas ok, donc pas ok, donc pas afficher")
} else {
    print("Deux conditions pas ok, donc pas ok, donc afficher car dans else")
}

// le == c'est égal à... et le != c'est différent de...
if num1 != num2 {
    print("cool on est différent")
}

// le inférieur ou égal
if num1 <= num2 {
    print("Oui je suis inférieur ou égal c'est bien ça")
}

// le meilleur pour la fin l'expression ternaire, on va décomposer:
// je déclare une variable ou une constante
// je lui affecte une expression ici num2 > num1
// si l'expression est vraie la constante vaut ce qui se trouve derrière ?
// sinon la constante vaut ce qui se trouve derrière :
let isBigger = num2 > num1 ? true : false
print("isBigger vaut \(isBigger)")
// if num2 > num1 {
//    isBigger = true
// } else {
//    isBigger = false
// }
// le if commenté est la même expression que le ternaire
{{< / highlight >}}