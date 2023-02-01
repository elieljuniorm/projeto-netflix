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

    <div class="containerResumo">
      <article class="conteudoResumo">
        <span class="titulo">Apresentação</span>
        <p class="resumo">
          O trabalho trará uma analise da plataforma de streaming Netflix para entender se as produções audiovisuais
          estão sendo disponibilizadas com acessibilidade as Pessoas com Deficiência Visual e assim garantindo ao
          usuário com deficiência visual em ter inclusão social e cultural por meio da plataforma. Busca entender se a
          garantia de usuário é assegurada pela Netflix ao entender a diversidade de público pagadora desse serviço e
          como as politicas de inclusão estão lidando com a diversidade. A pesquisa é realizada por meio de uma pesquisa
          bibliográfica e um estudo de caso sobre a Netflix e a acessibilidade aos deficientes visuais. Originando um
          resultado sobre o quantitativo de títulos que estão disponibilizados com audiodescrição e a comparação com a
          quantidade de títulos que a plataforma possui atualmente. Fazendo entender que esses dados são rotativos, pois
          a Netflix muda constantemente seus filmes e séries colocando ou retirando títulos de seu catálogo.
        </p>
      </article>
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

.logoNetflix {
  width: 20em;
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

.containerResumo {
  text-align: center;
  width: 80%;
}

.titulo {
  font-size: 18px;
  text-transform: uppercase;
  font-weight: bold;
}

.resumo {
  text-align: justify;
  padding: 1em 0;
  margin: 0;
}

@media only screen and (min-width: 1024px)  {
  .containerResumo {
    max-width: 80vh;
  }
}
</style>