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

 # Choix d’infrastructure
    
Les images vont être hébergées sur Firestore de Google. On utilisera également Firebase. Cela permet de déléguer l’infrastructure physique à un prestataire fiable. On évitera également des coûts astronomiques d’installation et de maintenance.

De plus, ces services peuvent être scalés pour répondre à un besoin croissant d’utilisateurs.

  

Le projet nécessite 2 développeurs : 2 x Back-end : chargés de la conception de l’API, et de la sécurité.
    

Le fait d’avoir seulement 2 développeurs permet une concentration accrue lors de la conception.

  

Les développeurs vont coûter 2500€ + charges d’entreprise par mois, ce qui revient à un total de 10000€ par mois en ressources humaines.

  

Sur firestore, la lecture de documents est gratuite jusqu’à 50000 par jour. On peut imaginer 1 million de lecture par jour si notre service est utilisé pour stocker des images de memes, ou de forums par exemple. Donc, au prix de 4.2 centimes pour 100k documents, on peut imaginer 42 centimes par jour, ce qui donne 12,6$ de frais de lecture par mois.

A cela on rajoute les frais de stockage. le Go coûte 18 centimes. Or, on peut estimer un stockage nécessaire de 10To le premier mois. Donc cela va nous coûter 1800$ de stockage par mois.

  

On va utiliser le NoSQL afin de pouvoir ressortir une image rapidement.
