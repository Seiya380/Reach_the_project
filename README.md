# Reach_the_project

The goal of this repository is to improve my skills in frameworks and working on my web architecture

First step :
I will look at React, Vue.js and svelte.

Status: I recheck the vue framework on their website.

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

    Limites : \* Coût à l'exécution (Runtime) : Le navigateur doit charger le moteur du framework (le "comparateur") et effectuer des calculs de comparaison à chaque changement. (voila pourquoi parfois les sites chargent a fond)

        Mémoire : Tu gardes deux versions de l'interface en mémoire (le vrai DOM et le virtuel).

2.  Le Compilateur DOM (Svelte) :

Svelte n'utilise pas de Virtual DOM. C'est un compilateur.

    Le concept : Tout le travail de "comparaison" se fait au moment où tu compiles ton code (avant d'envoyer le site sur internet). Svelte analyse ton code et génère des instructions JavaScript ultra-précises du type : "Si la variable count change, mets à jour uniquement le contenu de ce <span> précis".

    Pourquoi l'utiliser : * Performance brute : Pas de calculs de comparaison dans le navigateur. Les mises à jour sont chirurgicales et instantanées.

        Légèreté : Le site est beaucoup plus petit car tu n'envoies pas le "moteur" du framework à l'utilisateur, seulement ton code converti.

    Limites :

        Moins de flexibilité dynamique : Comme tout est décidé à la compilation, il est parfois plus complexe de créer des structures de composants totalement imprévisibles générées à la volée.
