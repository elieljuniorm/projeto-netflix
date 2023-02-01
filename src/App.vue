<template>
  <div>
    <ComponentHome />
    <ComponentFooter/>
  </div>
</template>

<script>
import ComponentHome from './components/ComponentHome.vue'
import ComponentFooter from './components/ComponentFooter.vue';

export default {
  name: 'App',
  components: {
    ComponentHome,
    ComponentFooter
  }
}
</script>

<style>
:root {
  --cor-linhas: #ffd700;
  --cor-cinza-padrao: #a3a3a3;
  --cor-preto-padrao: #000;
  --cor-preto-sombra: #141414;
  --cor-preto-grey: #363636;
  --cor-branco-gelo: #f1f1f1;
  --cor-branco-sombra: #dcdcdc;
  --margem: 100vh;
}

* {
  max-width: 100%;
  margin: auto;
  padding: 0;
  box-sizing: border-box;
  font-family: Arial, Helvetica, sans-serif;
  color: white;
}

html body {
  background-color: #000;
}

a {
  color: currentColor !important;
  text-decoration: unset !important;
  cursor: pointer !important;
}

li {
  list-style: none;
}
</style>