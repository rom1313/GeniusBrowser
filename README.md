# Genius JS (Browser Version)
<img src="https://zupimages.net/up/22/22/09ru.png" width="400" />
Genius est une bibliothèque de soutien pour le développement de vos applications.
Cette version est spécifique pour être utilisé en front-end

## Installation

Pour utiliser Genius-browser il suffit d'ajouter le script dans votre html.

```javascript
 <script src="https://unpkg.com/@rom13/genius-browser@1.0.38/index.js"></script>
```
>Attention pour éviter tout soucis, ne mettez pas le script en defer..

## Création d'un Genius :

Dans votre script créez une variable comme ceci :

```javascript
const genius = $
```
Il vous suffit désormais d'utiliser les fonctions du Genius

## Genius.date()

return la date formaté en français 

```javascript
let date = genius.date()
console.log(date); // return = 30/05/2022
```

## Genius.heure()

return l'heure correctement formaté

```javascript
let heure = genius.heure()
console.log(heure); // return = 00:04

let heurecomplete = genius.heure('complet')
console.log(heurecomplete); // return = 00:04:02
```

## Genius.nbaleatoire(maximum)

return un nombre aleatoire entre 1 et le nombre maximum (inclu !)

```javascript
let nombre = genius.nbaleatoire(12)
console.log(nombre); // return = 1 ou 2 ou 3........ou 12 !
```

## Genius.nbaleatoireminmax(minimum,maximum)

return un nombre aleatoire entre le nombre minimum et le nombre maximum (inclu !)

```javascript
let nombre = genius.nbaleatoireminmax(0,24)
console.log(nombre); // return = 0 ou 1 ou 2........ou 24 !
```
## Genius.recupnb(string,transformer)
Récupère uniquement les nombres d'un string et return le résultat
Transforme le résultat en type number (optionnel)

```javascript
let mot = "Le 34 c'est le sud"
console.log(genius.recupnb(mot)); // log 34

genius.recupnb(mot) // return 34 (type string)
genius.recupnb(mot,'transformer') // return 34 (type number)
```
## Genius.recupsommeObjet(option)
return la somme des propriétés d'un objet
```javascript
const objet = {
    nom: 'rom',
    nombre: 13,
    hobbie: 'art',
    code: 34
}

console.log(genius.recupsommeObjet(objet, 'string')); 
// ici on additionne les propriétés et on renvoi une version string
// return => rom 13 art 34
console.log(genius.recupsommeObjet(objet, 'number')); 
// ici on additionne les nombres entres eux et on renvoi la somme (type number)
// return 47 (13+34)
```

## Genius.moyenne(nb1,nb2,nb3,nb4,nb5,nb6,nb7,nb8,nb9,nb10)
Return la moyenne arrondi au centième près
2 nombres minimum, jusqu'à 10 nombres (optionnel)

```javascript
let moyenne = genius.moyenne(11, 11, 15, 18)
console.log(moyenne); // log 13.75
```

## Genius.bigmoyenne(tableau)
Return la moyenne arrondi au centième près
nombres illimités (array)

```javascript
let nb = [12, 12, 12, 45]
console.log(genius.bigmoyenne(nb)); // return 20.25
```

## Genius.intervallesecondes(secondes, fonction)
Créer un interval en secondes, et lance la fonction à chaques intervalles.

```javascript
function perso() {
    console.log('je suis un intervalle ! hihi')
    }
OU
const perso = () => {
    console.log('je suis un intervalle ! hihi')
    }

genius.intervallesecondes(1, perso) // log toutes les secondes (je suis un intervalle ! hihi)
```
## Genius.intervalleminutes(minutes, fonction)
Créer un interval en minutes, et lance la fonction à chaques intervalles.

```javascript
function perso() {
    console.log('je suis un intervalle ! hihi')
}

genius.intervalleminutes(1, perso) // log toutes les minutes (je suis un intervalle ! hihi)
```
## Genius.timeursecondes(secondes, fonction) 
Créer un timer en secondes, avant d'executer la fonction.

```javascript
function perso() {
    console.log('je suis un timer ! hoho')
}

genius.timeursecondes(5, perso) // log après 5 secondes (je suis un timer ! hoho)
```
## Genius.timeurminutes(minutes, fonction) 
Créer un timer en minutes, avant d'executer la fonction.

```javascript
function perso() {
    console.log('je suis un timer ! hoho')
}

genius.timeurminutes(2, perso) // log après 2 minutes (je suis un timer ! hoho)
```

## Genius.chronolog(debut) 
Créer un chrono qui s'affiche en console, qui débute par le nombre choisi.
Si aucun nombre est choisi il commencera par 1.

```javascript
genius.chronolog()  // log = 1 PUIS console.log = 2 PUIS console.log = 3 ....etc chaques secondes

genius.chronolog(6) // log = 6 PUIS console.log = 7 PUIS console.log = 8 ....etc chaques secondes

genius.chronologstop() // stop le chrono

genius.timeursecondes(5,genius.chronologstop) // exemple avec genius.timeursecondes, au bout de 5 secondes le chrono est stopppé.
```
## Genius.purifierstring(string) 
Nettoie un string qui contient des charactères spéciaux.

```javascript
let string = "Hey $je su'is un s*tring$$ avec ple)ins de symbo@les biza%rres^^ hihi."

console.log(genius.purifierstring(string))  // return : Hey je suis un string avec pleins de symboles bizarres hihi.
console.log(genius.purifierstring(3))  // return : erreur

if(genius.purifierstring(EXEMPLE)==='erreur'){  // exemple de condition
    // On sait que la valeur donné n'est pas un type string
}
```

## Genius.csscolor()
Créer un code css aléatoire de couleur

```javascript
let color = genius.csscolor() // return rgb(7,89,171) EXEMPLE
```

## Genius.fetchlog(url,fonction) 
Log la response de l'url, et lance la fonction après (optionnel)

```javascript
function mafonction() {
    // code de votre fonction
}
genius.fetchlog('https://API.com') 
// log response.data

genius.fetchlog('https://API.com', mafonction) 
// log response.data puis execute la fonction

```
## Genius.salaireSMIC(heures,option,log)
return ou log (optionnel) le salaire au SMIC arrondi

```javascript
genius.salaireSMIC(35,'brut') // return 1646
genius.salaireSMIC(35,'net')  // return 1304

genius.salaireSMIC(35,'brut','log') 
// log => Pour 35 heures, le salaire sera de 1646 euros (Brut)
genius.salaireSMIC(35,'net','log') 
// log => Pour 35 heures, le salaire sera de 1304 euros (Net)
```
## Genius.compareTAB(tab1,tab2,option)
return ou log (optionnel) si deux tableaux sont identiques
> Javascript renvoi false si on compare deux tableaux au contenu identique.
> Gebius.compareTAB renvoi true
```javascript
let tab = ['1', { prenom: 'tom', age: 18, tab: ['r', 5, { age: 11 }] }, '5', ['1', 2]]
let tab2 = ['1', { prenom: 'tom', age: 18, tab: ['r', 5, { age: 11 }] }, '5', ['1', 2]]

genius.compareTAB(tab, tab2) 
// return true
genius.compareTAB(tab, tab2,'log') 
// log => Vrai, les tableaux sont identiques
```
## Genius.textContent(valeur,selector,style)
Modifie le contenu (textcontent) et le style (optionnel) de votre élément HTML

```javascript

<p id="text"></p> // votre élément HTML (exemple)

let styledate = "font-size:35px;background-color:black;color:orange;text-align:center"
// le style voulu (optionnel)

genius.textContent(genius.date(),'#text',styledate)
// exemple avec Genius.date()

genius.textContent(genius.date(),'#text')
// Le style étant optionnel, vous pouvez juste modifier la valeur
```
>Exemple rendu avec le style : <img src="https://zupimages.net/up/22/24/a9c7.png" width="400" />

## ASTUCE : Afficher une heure dynamique
Utilisation de Genius.textContent() + Genius.heure() + requestAnimationFrame()
```javascript

//on créer la fonction 
function heureDynamique() {
    genius.textContent(genius.heure('complet'), '#text')
    requestAnimationFrame(heureDynamique)
}

//on appel "l'animation"
requestAnimationFrame(heureDynamique) 


```
Resultat : Votre heure est dynamique, elle se met à jour sans rechargement !

## Genius.event(selector,event,callback)
Créer un évènement sur l'élément HTML lance la fonction callback

```javascript

<button id="bouttontest">boutton</button>
// votre élément HTML (exemple)

function callback(e) {
    console.log(e.target.textContent); // log => 'boutton'

// ATTENTION CETTE FONCTION EST LA CALLBACK
// Elle ne peut prendre que (e) en paramètre
// Si vous souhaitez appeler des fonctions avec vos propres paramètres
// Insèrez les dans cette fonction
}

genius.event('#bouttontest', 'click', callback)
// On créer un écouteur au click sur l'element

// OU

genius.event('#bouttontest', 'click', (e)=>{
    console.log(e.target.textContent); // log => 'boutton'
    // Inserez vos fonctions...
})
```



Enjoy :sunglasses:

