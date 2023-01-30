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
</style>