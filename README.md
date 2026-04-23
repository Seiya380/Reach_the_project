# Reach the Project

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

Repo d'exploration et d'apprentissage des frameworks JavaScript front-end modernes. L'objectif : comprendre concrètement les différences entre React, Vue.js et Svelte avant de choisir un stack.

## Objectif

Comparer les approches **Virtual DOM** (React, Vue) et **Compilateur DOM** (Svelte) à travers la lecture de docs, de benchmarks et d'expérimentation pratique. Conclusion retenue : Svelte 5 avec les Runes.

## Structure des fichiers

```
Reach_the_project/
├── Roadmap.md          # Feuille de route et notes d'exploration
├── Project.md          # Journal de recherche : Virtual DOM vs Compilateur DOM
├── svelte.md           # Notes approfondies sur Svelte 5 / SvelteKit
├── vue.md              # Notes sur Vue.js et la Composition API
└── AlanTutorial/       # Bac à sable SvelteKit (projet pratique)
    ├── src/
    ├── package.json
    └── svelte.config.js
```

## Frameworks explorés

| Framework | Approche | Fichiers |
|---|---|---|
| React | Virtual DOM (bibliothèque) | — |
| Vue.js | Virtual DOM (framework) | `vue.md` |
| Svelte 5 | Compilateur DOM | `svelte.md`, `AlanTutorial/` |

## Ressources clés consultées

- [svelte.dev/blog/virtual-dom-is-pure-overhead](https://svelte.dev/blog/virtual-dom-is-pure-overhead)
- [krausest.github.io/js-framework-benchmark](https://krausest.github.io/js-framework-benchmark/)
- [svelte.dev/blog/runes](https://svelte.dev/blog/runes)
- [2024.stateofjs.com](https://2024.stateofjs.com)

## License

MIT © Seiya
