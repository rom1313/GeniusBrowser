# Genius JS (Browser Version)
<img src="https://zupimages.net/up/22/22/09ru.png" width="400" />
Genius est une bibliothèque de soutien pour le développement de vos applications.
Cette version est spécifique pour être utilisé en front-end

## Installation

Pour utiliser Genius-browser il suffit d'ajouter le script dans votre html.

```javascript
 <script src="https://unpkg.com/@rom13/genius-browser@1.0.20/index.js"></script>

```

Création d'un Genius :
Dans votre script créez une variable comme ceci :
```javascript
const genius = $
```
Il vous suffit désormais d'utiliser les fonction du Genius

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
Enjoy :sunglasses:

