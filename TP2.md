 # Convention de coding
    
### Définition de fonction
Dans les hooks React JS, il est possible de définir une fonction de deux façons :
-   `function myFunction() {}`
-   `const myFunction => () {}`
    
Dans un souci de régularité, il faut utiliser uniquement la première syntaxe. En effet, la deuxième syntaxe peut être confondue avec la définition d’une variable constante. De plus, la première est bien plus explicite.

### Optional chaining
En typescript, il est possible d’utiliser l’optional chaining afin de vérifier si une variable existe ou contient une valeur valide. Dans l’exemple suivant, le code JSX ne sera pas exécuté si la variable ou son parent n’existent pas, ou si leurs valeurs sont undefined.

    {
	    data?.name &&
	    <h1 children={data.name} />
    }

Il est donc de bonne pratique d’utiliser l’optional chaining.
  
### Utilisation des refs
Avec React Hooks, il est possible de stocker une valeur dans une ref, comme dans l’exemple ci-dessous :

    const myRef = useRef(“{‘title’: ‘hello’}”);
    debug(myRef.current);

Il est pertinent de faire cela au lieu d’utiliser un const dans un composant React, car au rafraîchissement du composant, la valeur ne sera pas effacée ou recalculée.

### Mettre les const en majuscules
Afin de pouvoir facilement identifier la nature d’un élément (variable ou constante), il faut systématiquement mettre les noms de constantes en majuscules.

    const WIDTH = 4;

### Fonctions utilitaires
Dans les fonctions utilitaires de la librairie interne, il faut toujours mettre des valeurs par défaut aux paramètres (dans la limite du possible). Cela permet à un utilisateur non initié de pouvoir tester la fonction.
