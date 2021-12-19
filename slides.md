---
theme: vuetiful
fonts: 
  sans: 'Quicksand'
  mono: 'JetBrains Mono'

highlighter: shiki
drawings:
  enabled: false
# show line numbers in code blocks
lineNumbers: true
# some information about the slides, markdown enabled
info: |
  ## ForEach Academy - B2 Frontend
  Slides du module FrontEnd et VueJs.

  Plus d'infos sur [foreach-academy.fr](https://www.foreach-academy.fr/formation-bachelor-developpement-web).
---
# Frontend et Vue.js
<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->
---
layout: section
---
# Comprendre l'écosystème frontend et JavaScript
<!--
outillage Javascript (bundlers, linters, frameworks...),
IDEs, DevTools, CLIs,
-->
---
layout: default
---
# Ecosystème Frontend (1995-2020)

<img src="/images/timeline.png" alt="Timeline des frameworks et langages" />
<div style="font-style: italic; text-align: center;">
  source: <a href="https://twitter.com/manz" target="_blank">twitter.com/manz</a>
</div>

<!--
- 2008: V8 JavaScript engine par Google
- 2009: NodeJS
- 2010: AngularJS
- 2013: ReactJS
- 2014: VueJS
-->
---
layout: default
cols: '1-1'
---
# Native JS

```html
<input class="name" value="" />
<p class="result"></p>
```

```js
const input = document.querySelector('.name')
const result = document.querySelector('.result')

input.addEventListener('change', (event) => {
  const newValue = event.target.value;
  result.textContent += newValue;
})
```

::right::

# VueJs

```html
<input class="name" v-model="result" />
<p> {{ result }} </p>
```

```js
data() {
  return {
    result: '',
  }
}
```

<!--
- Avoir un code plus déclaratif et lisible
- Enrichir son code (plugins)
- Optimiser et bénéficier d'un écosystème
-->
---
layout: default
---
# Bundler (Webpack, Rollup, Parcel...)

<img src="/images/bundler.png" alt="Schéma fonctionnel d'un bundler" />
<div style="font-style: italic; text-align: center;">
  source: <a href="https://webpack.js.org/" target="_blank">webpack.js.org</a>
</div>

<!--
- Entry: module depuis le quel résoudre le graphe de dépendances
- Output: bundle dénéré
- Loader: permet d'interprêter et convertir autre chose que JS/JSON en module.
- Plugin: effectuer des tâches (optimisation, injection...).
- Compatibility: générer un bundle ES5-compliant (IE11+).
-->
---
layout: two-cols
---
##  Vos nouveaux meilleurs amis

- <logos-mdn /> [MDN WebDocs JS](https://developer.mozilla.org/fr)
- <logos-vue /> [VueJS Docs](https://vuejs.org/)
- <logos-github-icon/> [VueJS GitHub](https://github.com/vuejs/vue)
- <logos-discord-icon /> [VueLand Discord](https://chat.vuejs.org/)

##
## Vos nouveaux outils favoris

- <logos-visual-studio-code /> [Visual Studio Code](https://code.visualstudio.com/)
- <logos-vue /> [Vue DevTools](https://devtools.vuejs.org/)
- <logos-terminal /> [Votre terminal](https://ohmyz.sh/)

## 
____

## 
> A vous de créer votre DX (Developer Experience), et de faire de votre environnement de travail votre meilleur allié.


::right::
 
<img style="height: 450px; margin: auto;" src="/images/docs-meme.png" alt="Meme 'read the docs' avec Phoebe et Joey" />

<!--
- Favoriser les documentations officielles
- Consulter les repos et issues des projets
- Rejoindre les communautés et canaux de discussion
- Eviter de recourir à Stack Overflow et autres
-->
---
layout: section
---

# Comprendre la philosophie de Vue.js
<!--
L'instance Vue,
Data et directives,
Methods, Computeds et Watchers,
-->
---
layout: default
---
# L'instance Vue

<iframe height="400" style="width: 100%;" scrolling="no" title="Vue JS instance" src="https://codepen.io/prazdevs/embed/zYdPvXz?default-tab=html%2Cresult&editable=true&theme-id=light" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/prazdevs/pen/zYdPvXz">
  Vue JS instance</a> by PraZ (<a href="https://codepen.io/prazdevs">@prazdevs</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

<!--
- Data
- Event
- Computed
- Methods
- Watcher
-->
---
layout: default
---
# L'instance Vue (complète)

<iframe height="400" style="width: 100%;" scrolling="no" title="Vue JS Instance (complète)" src="https://codepen.io/prazdevs/embed/PoJYNLa?default-tab=html%2Cresult&editable=true&theme-id=light" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/prazdevs/pen/PoJYNLa">
  Vue JS basics</a> by PraZ (<a href="https://codepen.io/prazdevs">@prazdevs</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

<!--
Exemple complet dispo sur les slides
-->
---
layout: default
---
# Pattern Model-View-ViewModel (MVVM)

<img style="height: 400px; margin:auto;" src="/images/mvvm.png" />
<div style="font-style: italic; text-align: center;">
  source: <a href="https://vuejs.org" target="_blank">vuejs.org</a>
</div>

---
layout: big-points
---

# En résumé, l'instance Vue:
- contrôle du HTML à partir d'un objet JavaScript.
- expose des données et méthodes au HTML.
- permet d'observer et de réagir à des actions.

---
layout: default
---
# Architecture en composants

<img style="height: 400px; margin:auto;" src="/images/component-architecture.png" />
<div style="font-style: italic; text-align: center;">
  source: <a href="https://vuejs.org" target="_blank">vuejs.org</a>
</div>

<!--
- Blocs de code réutilisable
- One-way data flow
- Props down / events up
-->
---
layout: section
---
# Créer une application avec les SFCs et l'Options API
<!--
Components et Slots,
Props et Events,
Mixins et Provide/Inject,
Cycle de vie d'un composant,
Data fetching,
-->
---
layout: default
---
# Vue-CLI

Vue-cli est un ensemble d'outils officiel fourni par Vue.  
C'est le standard dans la plupart des projets Vue 2.

- Création de projet interactive.
- Wrapper webpack préconfiguré et extensible (`vue-cli-service`).
- Installation de plugins et outils (`ESLint`, `VueX`...).
- GUI de gestion des apps et plugins.

Installer avec : `volta install @vue/cli`

Créer une application avec: `vue create <app-name>`

Lancer la GUI avec `vue ui`


<ri-arrow-right-circle-line /> [et la documentation est ici](https://cli.vuejs.org/)

---
layout: two-cols
---
# Single File Components

```html
<!-- index.html -->
<div id="app">
  <input v-model="searchInput" />
</div>
```
```js
// index.js
new Vue({
  el: '#app',
  data: {
    searchInput: '',
  },
});
```
```css
/* index.css */
input {
  color: red;
}
```

::right::

<v-click>

```vue
<!-- App.vue -->
<template>
  <div>
    <input v-model="searchInput" />
  </div>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        searchInput: '',
      }
    },
  }
</script>

<style scoped>
  input {
    color: red;
  }
</style>
```

</v-click>

<!-- 
- Réutilisable
- `data()` doit être une fonction
- Pas de `el`, seule la racine est montée dans le DOM, Vue résoud le reste
-->
---
layout: section
---
# Ajouter des fonctionnalités avec les Plugins
<!--
Comprendre l'API Plugin,
Router,
VueX,
Autres plugins (i18n, vuetify...),
-->
---
layout: section
---
# Tester son code dans une application Vue.js 
<!--
Comprendre le testing,
Jest et Vue-test-utils,
Ecrire des tests et suites de tests,
Mocker des composants et modules,
Autres méthodes de testing (composant, E2E),
-->
---
layout: section
---

# Adopter des bonnes pratiques avec Vue.js
<!--
Composants et SFCs,
Réusabilité,
Gestion de state et Stores,
Testing,
Réalité et compromis,
-->
---
layout: section
---
# Comprendre SSR et SSG avec le framework Nuxt
<!--
Le framework Nuxt,
Convention over configuration,
SSR (Server Side Rendering),
SSG (Static Site Generation),
-->
---
layout: section
---
# Aller plus loin avec Vue 3 et Vite
<!--
Vue 3 et la réactivité,
La Composition API,
SFCs avec <script setup>,
Vite et plugins,
-->
---
layout: section
---

# Améliorer son expérience développeur avec TypeScript

<!--
Comprendre TypeScript et son intérêt,
Intégrer TypeScript dans Vue 3,
-->

---
layout: section
---
# Comprendre les enjeux de l'accessibilité web
<!--
Comprendre ce qu'est l'accessibilité,
Des exemples d'implémentations inclusifs,
Développer son état d'esprit et son empathie,
-->
---
title: Merci d'avoir suivi jusque là!
showTitle: true
layout: outro
linkedin: 'linkedin.com/in/sachabouillez'
twitter: '@prazdevs'
website: 'praz.dev'
repository: 'github.com/prazdevs/foreach-b2-front'
---
Si vous avez une dernière question,   

c'est le moment!
