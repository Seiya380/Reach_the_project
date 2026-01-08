I'm actually do the tutorial from the framework svelte.

It seems that CSS is separated for each component.

It seems that we can use html string with {@html string} on the variable string.

<p>{@html string}</p>

I now being in advanced of the tutorial.

I have a statement for the logic $state.

Ok everything is quite predictible but probably not as I expected soon.

$props connu mais toujours aussi banger.

Fichiers .svelte (Les vues) : C'est là que je mets mon HTML. J'y appelles mes composants. Exemple : Card.svelte. etc...

Puis pour toute la logique js c'est soit dans un fichier .js soit dans un fichier .svelte.js si j'ai capté.

Fichiers .svelte.js (La logique réactive) un fichier JavaScript classique, utilisant les Runes ($state, $derived). peut aller partout a condition d'etre sous le format ci-dessus.

Exemple :  
 Je peux créer un compteur réactif dans un fichier .js et l'importer dans 10 composants différents. S'il change dans l'un, il change partout.

Pas de providers ni the Context API.

Ca semble cependant plus hardcode HTML que React.
