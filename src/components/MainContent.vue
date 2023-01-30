<template>
  <div id="app" class="container mt-3">
    <!-- filtro -->
    <b-form inline>

      <b-form-input id="inline-form-input-name" class="mb-2 mr-sm-2 mb-sm-0 colorInput" placeholder="Nome do filme"
        v-model="search" />

      <b-form-select class="mb-2 mr-sm-2 mb-sm-0 colorSelect" v-model="selected" :options="options" />

      <b-button title="Limpar filtro" v-b-tooltip.hover @click="clearFilter">
        <b-icon-trash class="icon" />
      </b-button>

    </b-form>

    <b-row>

      <b-col md="6" sm="12" class="tabela">
        <!-- tabela -->
        <b-table class="mt-3" striped hover :items="filteredItems" :fields="fields">
        </b-table>

      </b-col>

    </b-row>
  </div>
</template>

<script>
export default {
  name: "MainContent",
  data() {
    return {
      fields: [
        {
          key: "nome",
          label: "Nome do Filme ou Série",
        },
        {
          key: "isActive",
          label: "Gênero",
        },
      ],
      items: [
        {
          isActive: 'Ação',
          nome: "A princesa da yakuza"
        },
        {
          isActive: 'Ação',
          nome: "Agente oculto"
        },
        {
          isActive: 'Ação',
          nome: "Alerta vermelho"
        },
        {
          isActive: 'Ação',
          nome: "Army of the dead"
        },
        {
          isActive: 'Ação',
          nome: "Athena"
        },
        {
          isActive: 'Ação',
          nome: "Bala perdida 2"
        },
        {
          isActive: 'Ação',
          nome: "Cabra da peste"
        },
        {
          isActive: 'Ação',
          nome: "Enola holmes 1"
        },
        {
          isActive: 'Ação',
          nome: "Enola holmes 2"
        },
        {
          isActive: 'Ação',
          nome: "Esquadrão trovão"
        },
        {
          isActive: 'Ação',
          nome: "Hackers no controle"
        },
        {
          isActive: 'Ação',
          nome: "Interceptor"
        },
        {
          isActive: 'Ação',
          nome: "Lou"
        },
        {
          isActive: 'Ação',
          nome: "O homem de Toronto"
        },
        {
          isActive: 'Ação',
          nome: "O matador"
        },
        {
          isActive: 'Ação',
          nome: "O projeto adam"
        },
        {
          isActive: 'Ação',
          nome: "Os opostos sempre ..."
        },
        {
          isActive: 'Ação',
          nome: "Roubando Mussolini"
        },
        {
          isActive: 'Ação',
          nome: "Plano de aula – (12/12)"
        },
        {
          isActive: 'Ação',
          nome: "The seven Deadly Sins: fúria de Edimburgo 1 parte + (12/01)"
        },
        {
          isActive: 'Ação',
          nome: "Jung_e (23/01)"
        },
        {
          isActive: 'Anime',
          nome: "The seven Deadly Sins: fúria de Edimburgo 1 parte + (12/01)"
        },

        {
          isActive: 'Brasileiros',
          nome: "A princesa da yakuza"
        },
        {
          isActive: 'Brasileiros',
          nome: "Amor sem medida"
        },
        {
          isActive: 'Brasileiros',
          nome: "Barba, cabelo e bigode"
        },
        {
          isActive: 'Brasileiros',
          nome: "Brasil 2002 ..."
        },
        {
          isActive: 'Brasileiros',
          nome: "Cabras da peste"
        },
        {
          isActive: 'Brasileiros',
          nome: "Carnaval"
        },
        {
          isActive: 'Brasileiros',
          nome: "Cinderela pop"
        },
        {
          isActive: 'Brasileiros',
          nome: "Confissões de uma garota"
        },
        {
          isActive: 'Brasileiros',
          nome: "Democracia em vertigem"
        },
        {
          isActive: 'Brasileiros',
          nome: "Depois do universo"
        },
        {
          isActive: 'Brasileiros',
          nome: "Diários de intercambio"
        },
        {
          isActive: 'Brasileiros',
          nome: "Emicida ao vivo"
        },
        {
          isActive: 'Brasileiros',
          nome: "Emicida: é tudo pra ontem"
        },
        {
          isActive: 'Brasileiros',
          nome: "Esposa de aluguel"
        },
        {
          isActive: 'Brasileiros',
          nome: "Exterminadores"
        },
        {
          isActive: 'Brasileiros',
          nome: "Hoje eu quero voltar sozinho"
        },
        {
          isActive: 'Brasileiros',
          nome: "Kardec"
        },
        {
          isActive: 'Brasileiros',
          nome: "Laerte-se"
        },
        {
          isActive: 'Brasileiros',
          nome: "Lulli"
        },
        {
          isActive: 'Brasileiros',
          nome: "M-8: quando ..."
        },
        {
          isActive: 'Brasileiros',
          nome: "Modo avião"
        },
        {
          isActive: 'Brasileiros',
          nome: "O matador"
        },
        {
          isActive: 'Brasileiros',
          nome: "Os salafrários"
        },
        {
          isActive: 'Brasileiros',
          nome: "Pai em dobro"
        },
        {
          isActive: 'Brasileiros',
          nome: "Pelé"
        },
        {
          isActive: 'Brasileiros',
          nome: "Racionais: das ruas ..."
        },
        {
          isActive: 'Brasileiros',
          nome: "Ricos de amor"
        },
        {
          isActive: 'Brasileiros',
          nome: "Terapia do medo"
        },
        {
          isActive: 'Brasileiros',
          nome: "Tudo bem no natal que vem"
        },
        {
          isActive: 'Brasileiros',
          nome: "Um natal cheio de graça – (12/12)"
        },
        {
          isActive: 'Brasileiros',
          nome: "Vizinhos"
        },
        {
          isActive: 'Comédia',
          nome: "13: o musical"
        },
        {
          isActive: 'Comédia',
          nome: "A maldição de Bridge Hollow"
        },
        {
          isActive: 'Comédia',
          nome: "Afonso padilha ..."
        },
        {
          isActive: 'Comédia',
          nome: "Alerta vermelho"
        },
        {
          isActive: 'Comédia',
          nome: "Amor e gelato"
        },
        {
          isActive: 'Comédia',
          nome: "Amor em verona"
        },
        {
          isActive: 'Comédia',
          nome: "Amor sem medida – br"
        },
        {
          isActive: 'Comédia',
          nome: "Arremessando alto"
        },
        {
          isActive: 'Comédia',
          nome: "Barba, cabelo e bigode"
        },
        {
          isActive: 'Comédia',
          nome: "Barbie epic ..."
        },
        {
          isActive: 'Comédia',
          nome: "Bruna Louise"
        },
        {
          isActive: 'Comédia',
          nome: "Cabra da peste"
        },
        {
          isActive: 'Comédia',
          nome: "Carnaval – br"
        },
        {
          isActive: 'Comédia',
          nome: "Cinderela pop – br"
        },
        {
          isActive: 'Comédia',
          nome: "Combinação perfeita"
        },
        {
          isActive: 'Comédia',
          nome: "Como seria se...?"
        },
        {
          isActive: 'Comédia',
          nome: "Confissões de um ..."
        },
        {
          isActive: 'Comédia',
          nome: "Conselheira do amor (12/01)"
        },
        {
          isActive: 'Comédia',
          nome: "De férias da família"
        },
        {
          isActive: 'Comédia',
          nome: "De volta ao baile"
        },
        {
          isActive: 'Comédia',
          nome: "Dia do sim"
        },
        {
          isActive: 'Comédia',
          nome: "Diários de intercambio"
        },
        {
          isActive: 'Comédia',
          nome: "Ele acredita em papai noel! (12/01)"
        },
        {
          isActive: 'Comédia',
          nome: "Em busca de Ohana"
        },
        {
          isActive: 'Comédia',
          nome: "Encomenda para o natal – (12/12)"
        },
        {
          isActive: 'Comédia',
          nome: "Esposa de aluguel – br"
        },
        {
          isActive: 'Comédia',
          nome: "Esquadrão trovão"
        },
        {
          isActive: 'Comédia',
          nome: "Exterminadores do além: em busca da loira do banheiro"
        },
        {
          isActive: 'Comédia',
          nome: "Frangoelho ..."
        },
        {
          isActive: 'Comédia',
          nome: "Futebol em apuros"
        },
        {
          isActive: 'Comédia',
          nome: "Glass Onion: um mistério Knives Out (12/01)"
        },
        {
          isActive: 'Comédia',
          nome: "Ivy e bean"
        },
        {
          isActive: 'Comédia',
          nome: "Ivy e Bean: entram na dança "
        },
        {
          isActive: 'Comédia',
          nome: "Ivy e Bean: o fantasma do banheiro"
        },
        {
          isActive: 'Comédia',
          nome: "Justiceiras"
        },
        {
          isActive: 'Comédia',
          nome: "Klaus"
        },
        {
          isActive: 'Comédia',
          nome: "Lulli – br"
        },
        {
          isActive: 'Comédia',
          nome: "Marmaduque"
        },
        {
          isActive: 'Comédia',
          nome: "Mauricio meirelles"
        },
        {
          isActive: 'Comédia',
          nome: "Modo avião"
        },
        {
          isActive: 'Comédia',
          nome: "Moxie ..."
        },
        {
          isActive: 'Comédia',
          nome: "Natal com você"
        },
        {
          isActive: 'Comédia',
          nome: "O despertar ..."
        },
        {
          isActive: 'Comédia',
          nome: "O homem de Toronto"
        },
        {
          isActive: 'Comédia',
          nome: "O projeto adam"
        },
        {
          isActive: 'Comédia',
          nome: "Os opostos se atraem sempre"
        },
        {
          isActive: 'Comédia',
          nome: "Os salafrários "
        },
        {
          isActive: 'Comédia',
          nome: "Pai em dobro – br"
        },
        {
          isActive: 'Comédia',
          nome: "Pequenos grandes heróis "
        },
        {
          isActive: 'Comédia',
          nome: "Persuasão"
        },
        {
          isActive: 'Comédia',
          nome: "Ricos de amor"
        },
        {
          isActive: 'Comédia',
          nome: "Rodrigo Marques"
        },
        {
          isActive: 'Comédia',
          nome: "Rodrigo sant’anna"
        },
        {
          isActive: 'Comédia',
          nome: "Ruído branco (12/01)"
        },
        {
          isActive: 'Comédia',
          nome: "That’s amor"
        },
        {
          isActive: 'Comédia',
          nome: "Thiago ventura ..."
        },
        {
          isActive: 'Comédia',
          nome: "Tudo bem no natal que vem – br"
        },
        {
          isActive: 'Comédia',
          nome: "Um natal cheio de graça – (12/12)"
        },
        {
          isActive: 'Comédia',
          nome: "Uma queridinha de natal"
        },
        {
          isActive: 'Comédia',
          nome: "Vizinhos"
        },
        {
          isActive: 'Comédia',
          nome: "Wendell e wild"
        },
        {
          isActive: 'Comédia',
          nome: "Whindersson Nunes: adulto"
        },
        {
          isActive: 'Comédia',
          nome: "Whindersson nunes: é de..."
        },
        {
          isActive: 'Comédia',
          nome: "Yuri marçal"
        },

        {
          isActive: 'Comédia Stand-Up',
          nome: "Afonso Padilha: alma de pobre"
        },
        {
          isActive: 'Comédia Stand-Up',
          nome: "Bruna Louise: demolição"
        },
        {
          isActive: 'Comédia Stand-Up',
          nome: "Lugar de mulher"
        },
        {
          isActive: 'Comédia Stand-Up',
          nome: "Maurício Meirelles: levando o caos "
        },
        {
          isActive: 'Comédia Stand-Up',
          nome: "Rodrigo Marques: o inimigo do nível"
        },
        {
          isActive: 'Comédia Stand-Up',
          nome: "Rodrigo Sant’anna: cheguei¹"
        },
        {
          isActive: 'Comédia Stand-Up',
          nome: "Thiago Ventura: Pokas"
        },
        {
          isActive: 'Comédia Stand-Up',
          nome: "Whindersson Nunes: adulto"
        },
        {
          isActive: 'Comédia Stand-Up',
          nome: "Whindersson nunes: é de mim mesmo"
        },
        {
          isActive: 'Comédia Stand-Up',
          nome: "Yuri Marcal: ledo engano"
        },


      ],

      search: "",
      selected: null,
      options: [
        { value: null, text: "Selecione um gênero" },
        { value: 'Ação', text: "Ação" },
        { value: 'Anime', text: "Anime" },
        { value: "Brasileiros", text: "Brasileiros" },
        { value: "Comédia", text: "Comédia" },
        { value: "Comédia Stand-Up", text: "Comédia Stand-Up" },
        { value: "Documentários", text: "Documentários" },
        { value: "Drama", text: "Drama" },
        { value: "Estrangeiros", text: "Estrangeiros" },
        { value: "Ficção e fantasia", text: "Ficção e fantasia" },
        { value: "Música e musicais", text: "Música e musicais" },
        { value: "Para família toda", text: "Para família toda" },
        { value: "Romance", text: "Romance" },
        { value: "Séries", text: "Séries" },
        { value: "Suspense", text: "Suspense" },
        { value: "Terror", text: "Terror" },
      ],
    };
  },

  computed: {
    filteredItems() {
      let items = [];
      items = this.items.filter((item) => {
        return (
          item.nome.toLowerCase().indexOf(this.search.toLowerCase()) > -1
        );
      });

      items = items.filter((item) => {
        if (this.selected == null) return item;
        return item.isActive === this.selected;
      });

      return items;
    },
  },

  methods: {
    clearFilter() {
      this.search = "";
      this.selected = null;
    },
  },
};
</script>

<style>
.tabela {
  color: white !important;
}

.colorInput,
.colorSelect {
  color: #f8f9fa !important;
  background: #212529 !important;
}
</style>
