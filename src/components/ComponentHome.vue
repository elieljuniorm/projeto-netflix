<template>
  <div class="containerHome">
    <img class="logoNetflix" src="@/assets/netflix-gif.gif" alt="Logo Netflix">

    <MainContent />

  </div>
</template>

<script>
import MainContent from './MainContent.vue';

export default {
  name: "ComponentHome",
  components: { MainContent },
}
</script>


<style scoped>
.containerHome {
  display: grid;
  align-items: center;
}

.logoNetflix {
  width: 20em;
}

h1 {
  color: white;
}

.conteudoMain {
  display: flex;
  background-color: #FFFFFF;
  border-radius: 10px;
  width: 80%;
}

.navabarLateral {
  width: 5em;
  height: 27em;
}

.conteudoCentral {
  width: 25em;
  height: 27em;
  background-color: #F6F6F6;
}
</style>
