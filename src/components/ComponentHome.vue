<template>
  <div class="containerHome">
    <img class="logoNetflix" src="@/assets/netflix-gif.gif" alt="Logo Netflix">

    <h1>EM BUSCA PELA AUDIODESCRIÇÃO: A GARANTIA DE USUÁRIO COM DEFICIÊNCIA VISUAL NA NETFLIX</h1>

    <div class="box-buttons">
      <a href="http://" target="_blank" rel="noopener noreferrer" class="link btn btn-efeito">
        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="17" fill="currentColor"
          class="bi bi-file-earmark-break-fill" viewBox="0 0 16 16">
          <path
            d="M4 0h5.293A1 1 0 0 1 10 .293L13.707 4a1 1 0 0 1 .293.707V9H2V2a2 2 0 0 1 2-2zm5.5 1.5v2a1 1 0 0 0 1 1h2l-3-3zM2 12h12v2a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2v-2zM.5 10a.5.5 0 0 0 0 1h15a.5.5 0 0 0 0-1H.5z" />
        </svg>
        Link do artigo
      </a>
    </div>

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

h1 {
  margin: 0 2em;
  text-align: center;
  font-size: 20px;
}

.box-buttons {
  width: 100%;
  height: 100%;
  float: left;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 1em 0;
}

.btn {

  width: 100%;
  line-height: 40px;
  max-width: 160px;
  font-size: 1em;
  color: #fff;
  cursor: pointer;
  display: block;
  border-radius: 50px;
  text-align: center;
  position: relative;
  text-decoration: none;
  vertical-align: middle;
  float: left;

}

.btn:hover {
  text-decoration: none;
}

.btn-efeito {
  overflow: hidden;
  position: relative;
  background-color: #095599;
}

.btn-efeito:hover {
  background-color: #0073d9;
}

.btn-efeito span {
  z-index: 20;
}

.btn-efeito:after {
  background: #fff;
  content: "";
  height: 155px;
  left: -85px;
  opacity: .4;
  position: absolute;
  top: -60px;
  -webkit-transform: rotate(30deg);
  transform: rotate(30deg);
  -webkit-transition: all 850ms cubic-bezier(0.19, 1, 0.22, 1);
  transition: all 850ms cubic-bezier(0.19, 1, 0.22, 1);
  width: 70px;
  z-index: 1;
}

.btn-efeito:hover:after {
  left: 130%;
  -webkit-transition: all 850ms cubic-bezier(0.19, 1, 0.22, 1);
  transition: all 850ms cubic-bezier(0.19, 1, 0.22, 1);
}

/*Adicione esta classe se for usar 2 Botões*/
.margin-right {
  margin-right: 10px;
}

.logoNetflix {
  width: 20em;
}
</style>