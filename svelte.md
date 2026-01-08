Voici la traduction de ton message initial en français :

« Je suis actuellement en train de suivre le tutoriel du framework Svelte.

Il semble que le CSS soit isolé (scopé) pour chaque composant.

Il semble aussi que l'on puisse utiliser des chaînes de caractères HTML avec la syntaxe {@html chaine} sur une variable de type string :

<p>{@html chaine}</p>

Je suis maintenant arrivé à un stade avancé du tutoriel.

J'utilise la déclaration $state pour la logique de réactivité.

D'accord, tout est assez prévisible, mais probablement pas de la manière à laquelle je m'attendais au départ.

$props connu mais toujours aussi banger.

Fichiers .svelte (Les vues) : C'est là que je mets mon HTML. J'y appelles mes composants. Exemple : Card.svelte. etc...

Puis pour toute la logique js c'est soit dans un fichier .js soit dans un fichier .svelte.js si j'ai capté.

Fichiers .svelte.js (La logique réactive) un fichier JavaScript classique, utilisant les Runes ($state, $derived). peut aller partout a condition d'etre sous le format ci-dessus.

Exemple :  
 Je peux créer un compteur réactif dans un fichier .js et l'importer dans 10 composants différents. S'il change dans l'un, il change partout.

Pas de providers ni the Context API.

Ca semble cependant plus hardcode HTML que React.
