# Reach_the_project

Le but du repo est de comprendre ce que signifie les differents webcomponents et les frameworks supporte

First step :
Regarder Svelte, vue.js, react

Status: Je selectionne et utilise svelte5

J'ai une question sur le framework DOM.

C'est quoi la difference entre un compilateur DOM et un virtual DOM ? Et quel avantages inconvenient ?

Selon

- Lien : svelte.dev/blog/virtual-dom-is-pure-overhead

- legacy.reactjs.org/docs/reconciliation.html

- krausest.github.io/js-framework-benchmark/

- svelte.dev/blog/runes

-2024.stateofjs.com

1.  Le Virtual DOM (React, Vue) est une copie légère de l'interface stockée en mémoire.

    Le concept : Quand une donnée change, le framework ne sait pas exactement où le changement doit avoir lieu. Il crée donc un nouvel arbre virtuel complet, le compare à l'ancien (diffing), calcule les différences, puis envoie les instructions de mise à jour au vrai navigateur.

    Pourquoi l'utiliser : C'est extrêmement flexible. Tu peux manipuler ton interface comme des objets JavaScript purs sans te soucier de la performance brute, car les frameworks "optimisent" les changements pour toi.

    Limites : Coût à l'exécution (Runtime) : Le navigateur doit charger le moteur du framework (le "comparateur") et effectuer des calculs de comparaison à chaque changement. (voila pourquoi parfois les sites chargent a fond)

        Mémoire : Tu gardes deux versions de l'interface en mémoire (le vrai DOM et le virtuel).

2.  Le Compilateur DOM (Svelte) :

Svelte n'utilise pas de Virtual DOM. C'est un compilateur.

    Le concept : Tout le travail de "comparaison" se fait au moment où tu compiles ton code (avant d'envoyer le site sur internet). Svelte analyse ton code et génère des instructions JavaScript ultra-précises du type : "Si la variable count change, mets à jour uniquement le contenu de ce <span> précis".

    Pourquoi l'utiliser : Performance brute : Pas de calculs de comparaison dans le navigateur. Les mises à jour sont chirurgicales et instantanées.

        Légèreté : Le site est beaucoup plus petit car tu n'envoies pas le "moteur" du framework à l'utilisateur, seulement ton code converti.

    Limites :

        Moins de flexibilité dynamique : Comme tout est décidé à la compilation, il est parfois plus complexe de créer des structures de composants totalement imprévisibles générées à la volée.

Donc En gros pour faire simple, React, Vue.js et Svelte sont des frameworks diamétralement différents:

React n'est pas un framework complet mais une bibliothèque (litteralement).

    Flexibilité dynamique : C'est le plus permissif. Comme il utilise le JSX, on peux manipuler les composants comme de simples variables.

    Contrôle du DOM : Utilise le Virtual DOM. Les mises à jour sont gérées via un cycle de ré-exécution des fonctions (le "re-render" ou diffing).

    Structure : Très libre. Il n'y a pas de dossier "officiel" pour les composants. Tout est basé sur les Hooks (useState, useEffect).

    Gestion du CSS :

        CSS-in-JS : Très populaire (Styled Components, Emotion).

        Utilitaire : Domination massive de Tailwind CSS.

        Modules : Fichiers .module.css pour isoler les styles.

    Ressources : Immenses. Si il a un bug, la solution existe déjà sur StackOverflow ou via une IA.

Vue (l'entre deux il s'assume pas trop) Il offre un cadre plus structuré cependant.

    Flexibilité & DOM : Comme React, il utilise un Virtual DOM. La réactivité est gérée par des "Proxies" JavaScript qui surveillent les changements de données.

    Système de composants : Utilise les fichiers .vue avec trois blocs distincts : <template>, <script> (souvent avec la Composition API) et <style>.

    Routing & État : Contrairement à React, Vue propose des solutions "officielles" (Vue Router, Pinia pour l'état) qui sont parfaitement intégrées et maintenues.

    Gestion du CSS :

        Scoped CSS : Natif et très puissant via la balise <style scoped>. Le framework s'occupe de l'isolation automatiquement.

        Support natif : Très facile d'intégrer du SASS/LESS directement dans le composant.

Svelte change radicalement la donne (le chouchou des devs).

    Approche unique : Ce n'est pas une bibliothèque qu'on appelle, c'est un compilateur. Il transforme le code en JavaScript natif qui manipule directement le DOM sans passer par un intermédiaire (pas de Virtual DOM).

    Réactivité chirurgicale : Avec Svelte 5 et les Runes ($state), la réactivité est explicite. On ne dis pas "re-render tout le composant", le compilateur sait exactement quelle ligne de HTML modifier.

    Système de fichiers : Utilise .svelte. Très proche du HTML standard. Pas besoin de fonctions complexes pour gérer les boucles ou les conditions ({#each}, {#if}).

    Gestion du CSS :

        Isolation totale par défaut : Le CSS est automatiquement "scopé" au composant.

        Optimisation : Le compilateur supprime automatiquement les règles CSS que tu n'utilises pas dans ton fichier, réduisant ainsi le poids final.

Conclusion :

En vrai de vrai, Svelte c'est patate quand meme. Genre comment ca en terme de reactivite c'est mieux. React, Pas si reactif que ca. Vue, en vrai c'est le moins assume.

En plus j'ai tester et quand tu foire bah si ca marche pas ca marche pas mais c'est clean en vrai comme resoudre un casse tete. Compare a react ou il te lisse le poil du cul.

Je suis actuellement en train de tester svelte sur mon VScode mais bordel comment les liens se font ? genre j'ai pris un blank page ou j'ai juste "+layout.svelte" et "+page.svelte" mais les app.html qui va devenir un dom possedent plutot: 

<!doctype html>
<html lang="en">
	<head>
		<meta charset="utf-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1" />
		%sveltekit.head%
	</head>
	<body data-sveltekit-preload-data="hover">
		<div style="display: contents">%sveltekit.body%</div>
	</body>
</html>
C'est bizarre car il appelle svelkit.{file}, mais je n'arrive pas a trouver les symbolique qui redirige aux bons fichiers. 

Je viens de comprendre l'architecture de sveltekit. au moins je sais comment ca fonctionne, je ne saisis pas encore comment il appelle node 0/1/2.js mais j'ai deja la structure initiale et je viens de capter que je suis sur sveltekit et non svelte raw. donc je vais restart. Alors, j'ai oublie comment avoir le raw svelte. Donc c'est bon je l'ai plus en raw et j'ai la config officiel. j'ai cree un nouveau dossier appelle Alan Tutorial qui me permettra de faire mon bac a sable.

Ok maintenant que j'ai compris le fonctionnement, je dois a present naviguer entre deux fichiers. Je vais me referer a la doc.