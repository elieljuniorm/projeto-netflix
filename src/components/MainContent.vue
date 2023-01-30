<template>
  <div id="app" class="container mt-3">
    <!-- filtro -->
    <b-form inline class="search">

      <b-form-input id="inline-form-input-name" class="mb-2 mr-sm-2 mb-sm-0 colorInput" placeholder="Nome do filme"
        v-model="search" />

      <b-form-select class="mb-2 mr-sm-2 mb-sm-0 colorSelect" v-model="selected" :options="options" />

      <b-button title="Limpar filtro" v-b-tooltip.hover @click="clearFilter">
        <b-icon-trash class="icon" />
      </b-button>

    </b-form>

    <b-row class="tabelaMain">

      <b-col md="6" sm="12" class="tabelaCor">
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
        {
          isActive: 'Documentário',
          nome: "3 toneladas: assalto ao banco central – br"
        },
        {
          isActive: 'Documentário',
          nome: "Além do som"
        },
        {
          isActive: 'Documentário',
          nome: "Amor no espectro: EUA"
        },
        {
          isActive: 'Documentário',
          nome: "Anitta: made in Honório – br"
        },
        {
          isActive: 'Documentário',
          nome: "Audible"
        },
        {
          isActive: 'Documentário',
          nome: "Bandidos na TV"
        },
        {
          isActive: 'Documentário',
          nome: "Brasil 2002: os bastidores do penta"
        },
        {
          isActive: 'Documentário',
          nome: "Cena de crime: o campo de morte do texas"
        },
        {
          isActive: 'Documentário',
          nome: "Cena do crime: mistérios e morte no hotel Cecil"
        },
        {
          isActive: 'Documentário',
          nome: "Cena do crime: o assassino da Times Square"
        },
        {
          isActive: 'Documentário',
          nome: "Crip camp: revolução para inclusão"
        },
        {
          isActive: 'Documentário',
          nome: "Democrata em vertigem – br"
        },
        {
          isActive: 'Documentário',
          nome: "Elize matsunaga: era um vez o crime – br"
        },
        {
          isActive: 'Documentário',
          nome: "Emicida amar ..."
        },
        {
          isActive: 'Documentário',
          nome: "Emicida: é tudo pra ontem"
        },
        {
          isActive: 'Documentário',
          nome: "Fearless: 8 segundos para a glória"
        },
        {
          isActive: 'Documentário',
          nome: "João de deus: cura e crime – br"
        },
        {
          isActive: 'Documentário',
          nome: "La casa de papel: de Tóquio a Berlim"
        },
        {
          isActive: 'Documentário',
          nome: "La casa de papel: el fenômeno"
        },
        {
          isActive: 'Documentário',
          nome: "Laerte-se"
        },
        {
          isActive: 'Documentário',
          nome: "Meu amor: seis histórias de amor verdadeiro"
        },
        {
          isActive: 'Documentário',
          nome: "Meu encontro com o mal"
        },
        {
          isActive: 'Documentário',
          nome: "Minha história"
        },
        {
          isActive: 'Documentário',
          nome: "Mundo mistério"
        },
        {
          isActive: 'Documentário',
          nome: "Neymar: o caos perfeito - br"
        },
        {
          isActive: 'Documentário',
          nome: "O amor no espectro"
        },
        {
          isActive: 'Documentário',
          nome: "O time da redenção"
        },
        {
          isActive: 'Documentário',
          nome: "Pelé – br"
        },
        {
          isActive: 'Documentário',
          nome: "Pódio para todos"
        },
        {
          isActive: 'Documentário',
          nome: "Racionais ..."
        },
        {
          isActive: 'Documentário',
          nome: "Roubos inacreditáveis"
        },
        {
          isActive: 'Documentário',
          nome: "Street food: américa latina "
        },
        {
          isActive: 'Documentário',
          nome: "Vai Anitta – br"
        },
        {
          isActive: 'Drama',
          nome: "A caminho do verão"
        },
        {
          isActive: 'Drama',
          nome: "Ainda estou aqui"
        },
        {
          isActive: 'Drama',
          nome: "Arremessando alto"
        },
        {
          isActive: 'Drama',
          nome: "As nadadoras – (12/12)"
        },
        {
          isActive: 'Drama',
          nome: "Athena"
        },
        {
          isActive: 'Drama',
          nome: "Bala perdida 2"
        },
        {
          isActive: 'Drama',
          nome: "Bird box"
        },
        {
          isActive: 'Drama',
          nome: "Como seria se...?"
        },
        {
          isActive: 'Drama',
          nome: "Continência do amor"
        },
        {
          isActive: 'Drama',
          nome: "Depois do universo"
        },
        {
          isActive: 'Drama',
          nome: "Dois papas"
        },
        {
          isActive: 'Drama',
          nome: "Enola holmes 1"
        },
        {
          isActive: 'Drama',
          nome: "Enola holmes 2"
        },
        {
          isActive: 'Drama',
          nome: "Hoje eu quero voltar ..."
        },
        {
          isActive: 'Drama',
          nome: "Imperdoável "
        },
        {
          isActive: 'Drama',
          nome: "Kardec"
        },
        {
          isActive: 'Drama',
          nome: "Ligações perigosas"
        },
        {
          isActive: 'Drama',
          nome: "Lou"
        },
        {
          isActive: 'Drama',
          nome: "M-8: quando a noite"
        },
        {
          isActive: 'Drama',
          nome: "Moxie: quando as garotas vão à luta"
        },
        {
          isActive: 'Drama',
          nome: "Nada de novo no front"
        },
        {
          isActive: 'Drama',
          nome: "O amante de Lady Chatterley – (12/12)"
        },
        {
          isActive: 'Drama',
          nome: "O caderno do Tony"
        },
        {
          isActive: 'Drama',
          nome: "O céu da meia-noite "
        },
        {
          isActive: 'Drama',
          nome: "O diário de noel (12/01)"
        },
        {
          isActive: 'Drama',
          nome: "O enfermeiro da noite"
        },
        {
          isActive: 'Drama',
          nome: "O milagre"
        },
        {
          isActive: 'Drama',
          nome: "O pálido olho azul (12/01)"
        },
        {
          isActive: 'Drama',
          nome: "O perfumista"
        },
        {
          isActive: 'Drama',
          nome: "O telefone do Sr. Harrigan"
        },
        {
          isActive: 'Drama',
          nome: "Olá adeus e tudo mais"
        },
        {
          isActive: 'Drama',
          nome: "Pai em dobro"
        },
        {
          isActive: 'Drama',
          nome: "Perdoai-nos as nossas ofensas"
        },
        {
          isActive: 'Drama',
          nome: "Persuasão"
        },
        {
          isActive: 'Drama',
          nome: "Rainbow"
        },
        {
          isActive: 'Drama',
          nome: "Roubando Mussolini"
        },
        {
          isActive: 'Drama',
          nome: "Ruído branco (12/01)"
        },
        {
          isActive: 'Drama',
          nome: "Uma garota de muita sorte"
        },
        {
          isActive: 'Drama',
          nome: "Jung_e"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Athena"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Através da minha janela – (12/12)"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Bala perdida 2"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Conselheira do amor (12/01)"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Encomenda para o natal –(12/12)"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Hackers no controle"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Lar dos esquecidos"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Ligações perigosas"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Nada de novo no front"
        },
        {
          isActive: 'Estrangeiros',
          nome: "O monastério "
        },
        {
          isActive: 'Estrangeiros',
          nome: "O perfumista"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Os opostos sempre se atraem"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Plano de aula – (12/12)"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Rainbow"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Roubando Mussolini"
        },
        {
          isActive: 'Estrangeiros',
          nome: "Jung_e"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "A maldição de Bridge Hollow"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "Bird box"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "Escola do bem e do mal"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "Futebol em apuros"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "O céu da meia-noite"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "O despertar das Tartarugas ninjas: o filme"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "O projeto Adam"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "Rainbow"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "Spiderhead"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "The seven Deadly Sins: fúria de Edimburgo 1 parte (12/01)"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "Wendell e wild"
        },
        {
          isActive: 'Ficção e fantasia',
          nome: "Jung_e"
        },
        {
          isActive: 'Música e musicais',
          nome: "13: o musical"
        },
        {
          isActive: 'Música e musicais',
          nome: "A caminho da lua"
        },
        {
          isActive: 'Música e musicais',
          nome: "Anitta: mande in Honorio – br"
        },
        {
          isActive: 'Música e musicais',
          nome: "Carnaval – br"
        },
        {
          isActive: 'Música e musicais',
          nome: "Coisa linda – br"
        },
        {
          isActive: 'Música e musicais',
          nome: "Continência do amor"
        },
        {
          isActive: 'Música e musicais',
          nome: "É o amor: família Camargo – br"
        },
        {
          isActive: 'Música e musicais',
          nome: "Emicida amar e elo: ao vivo - br"
        },
        {
          isActive: 'Música e musicais',
          nome: "Emicida: é tudo pra ontem - br"
        },
        {
          isActive: 'Música e musicais',
          nome: "Matilda: o músical (12/01)"
        },
        {
          isActive: 'Música e musicais',
          nome: "Racionais: das ruas de SP para o mundo - br"
        },
        {
          isActive: 'Música e musicais',
          nome: "Rainbow"
        },
        {
          isActive: 'Música e musicais',
          nome: "Scrooger: um conto de natal – (12/12)"
        },
        {
          isActive: 'Música e musicais',
          nome: "Sintonia – br"
        },
        {
          isActive: 'Música e musicais',
          nome: "So se for por amor"
        },
        {
          isActive: 'Música e musicais',
          nome: "Vai Anitta – br"
        },
        {
          isActive: 'Para a família toda',
          nome: "13: o musical"
        },
        {
          isActive: 'Para a família toda',
          nome: "A caminho da lua"
        },
        {
          isActive: 'Para a família toda',
          nome: "Barbie Epic Road Trip (Interativo)"
        },
        {
          isActive: 'Para a família toda',
          nome: "Chip e potato"
        },
        {
          isActive: 'Para a família toda',
          nome: "Cinderela pop – br"
        },
        {
          isActive: 'Para a família toda',
          nome: "Confissões de uma garota excluída – Br"
        },
        {
          isActive: 'Para a família toda',
          nome: "Dia do sim"
        },
        {
          isActive: 'Para a família toda',
          nome: "Em busca de Ohana"
        },
        {
          isActive: 'Para a família toda',
          nome: "Fera do mar"
        },
        {
          isActive: 'Para a família toda',
          nome: "Fragoelho: o hamster das trevas"
        },
        {
          isActive: 'Para a família toda',
          nome: "Futebol em apuros"
        },
        {
          isActive: 'Para a família toda',
          nome: "Ivy e Bean"
        },
        {
          isActive: 'Para a família toda',
          nome: "Ivy e Bean: entram na dança "
        },
        {
          isActive: 'Para a família toda',
          nome: "Ivy e Bean: o fantasma do banheiro"
        },
        {
          isActive: 'Para a família toda',
          nome: "Klaus"
        },
        {
          isActive: 'Para a família toda',
          nome: "Marmaduke"
        },
        {
          isActive: 'Para a família toda',
          nome: "Matilda: o músical (12/01)"
        },
        {
          isActive: 'Para a família toda',
          nome: "Natal com você"
        },
        {
          isActive: 'Para a família toda',
          nome: "Nosso natal em família– (12/12)"
        },
        {
          isActive: 'Para a família toda',
          nome: "O despertar das Tartarugas ninjas: o filme"
        },
        {
          isActive: 'Para a família toda',
          nome: "O dragão do meu pai"
        },
        {
          isActive: 'Para a família toda',
          nome: "Os patrulheiros em ação: salvam o natal – (12/12)"
        },
        {
          isActive: 'Para a família toda',
          nome: "Pai em dobro -  br"
        },
        {
          isActive: 'Para a família toda',
          nome: "Pequenos grandes heróis"
        },
        {
          isActive: 'Para a família toda',
          nome: "Scrooge: um conto de natal – (12/12)"
        },
        {
          isActive: 'Para a família toda',
          nome: "Terra dos sonhos – (12/12)"
        },
        {
          isActive: 'Romance',
          nome: "A caminho do verão"
        },
        {
          isActive: 'Romance',
          nome: "Ainda estou aqui"
        },
        {
          isActive: 'Romance',
          nome: "Amor e gelato"
        },
        {
          isActive: 'Romance',
          nome: "Amor em verona"
        },
        {
          isActive: 'Romance',
          nome: "Amor sem medida – br"
        },
        {
          isActive: 'Romance',
          nome: "Através da minha janela – (12/12)"
        },
        {
          isActive: 'Romance',
          nome: "Combinação perfeita"
        },
        {
          isActive: 'Romance',
          nome: "Como seria se...?"
        },
        {
          isActive: 'Romance',
          nome: "Conselheira do amor - (12/01)"
        },
        {
          isActive: 'Romance',
          nome: "Continência do amor"
        },
        {
          isActive: 'Romance',
          nome: "Dá adeus e tudo mais"
        },
        {
          isActive: 'Romance',
          nome: "Depois do universo – br"
        },
        {
          isActive: 'Romance',
          nome: "Diário de intercâmbio - BR"
        },
        {
          isActive: 'Romance',
          nome: "Ele acredita no papai noel! (12/01)"
        },
        {
          isActive: 'Romance',
          nome: "Encomenda para o natal – (12/12)"
        },
        {
          isActive: 'Romance',
          nome: "Esposa de aluguel – br"
        },
        {
          isActive: 'Romance',
          nome: "Hoje eu quero voltar sozinho – br"
        },
        {
          isActive: 'Romance',
          nome: "Ligações perigosas"
        },
        {
          isActive: 'Romance',
          nome: "Modo avião – Br"
        },
        {
          isActive: 'Romance',
          nome: "Natal com você"
        },
        {
          isActive: 'Romance',
          nome: "O amante de Lady Chatterley – (12/12)"
        },
        {
          isActive: 'Romance',
          nome: "O diário de noel – (12/12)"
        },
        {
          isActive: 'Romance',
          nome: "Persuasão"
        },
        {
          isActive: 'Romance',
          nome: "Ricos de amor"
        },
        {
          isActive: 'Romance',
          nome: "That’s amor"
        },
        {
          isActive: 'Romance',
          nome: "Um natal cheio de graça –  (12/12)"
        },
        {
          isActive: 'Romance',
          nome: "Uma queridinha de natal"
        },
        {
          isActive: 'Série',
          nome: "1899 – (12/12)"
        },
        {
          isActive: 'Série',
          nome: "3 toneladas: assalto ao banco central"
        },
        {
          isActive: 'Série',
          nome: "3%"
        },
        {
          isActive: 'Série',
          nome: "A sogra que te pariu – br"
        },
        {
          isActive: 'Série',
          nome: "Além do som"
        },
        {
          isActive: 'Série',
          nome: "Amor no espectro"
        },
        {
          isActive: 'Série',
          nome: "Amor no espectro EUA"
        },
        {
          isActive: 'Série',
          nome: "Anatomia de um escândalo "
        },
        {
          isActive: 'Série',
          nome: "Anitta: mande in Honório"
        },
        {
          isActive: 'Série',
          nome: "Bandidos na TV – br"
        },
        {
          isActive: 'Série',
          nome: "Bem-vindos ao éden"
        },
        {
          isActive: 'Série',
          nome: "Blockbuster"
        },
        {
          isActive: 'Série',
          nome: "Boca a boca"
        },
        {
          isActive: 'Série',
          nome: "Bom dia, verônica – br"
        },
        {
          isActive: 'Série',
          nome: "Boo Bitch"
        },
        {
          isActive: 'Série',
          nome: "Bridgerton"
        },
        {
          isActive: 'Série',
          nome: "Brincando com fogo Brasil – br"
        },
        {
          isActive: 'Série',
          nome: "Brown e sua turma (12/01)"
        },
        {
          isActive: 'Série',
          nome: "Casamentos as cegas Brasil – br"
        },
        {
          isActive: 'Série',
          nome: "Cena de crime: mistério e morte..."
        },
        {
          isActive: 'Série',
          nome: "Cena de crime: o campo de morte do texas"
        },
        {
          isActive: 'Série',
          nome: "Cena do crime: o assassino da times square"
        },
        {
          isActive: 'Série',
          nome: "Chip e potato"
        },
        {
          isActive: 'Série',
          nome: "Chip e potato 2"
        },
        {
          isActive: 'Série',
          nome: "Cidade invisível "
        },
        {
          isActive: 'Série',
          nome: "Coisa mais linda"
        },
        {
          isActive: 'Série',
          nome: "Crisálida"
        },
        {
          isActive: 'Série',
          nome: "Dahmer: um canibal americano"
        },
        {
          isActive: 'Série',
          nome: "Daniel: o caçador de magia"
        },
        {
          isActive: 'Série',
          nome: "De volta aos 15"
        },
        {
          isActive: 'Série',
          nome: "É o amor: família Camargo - br"
        },
        {
          isActive: 'Série',
          nome: "Echoes"
        },
        {
          isActive: 'Série',
          nome: "Elite"
        },
        {
          isActive: 'Série',
          nome: "Elite histórias breves: Carla e Samuel"
        },
        {
          isActive: 'Série',
          nome: "Elite histórias breves: Guzmám, Caue e Rebe"
        },
        {
          isActive: 'Série',
          nome: "Elite histórias breves: nádia e Guzmán"
        },
        {
          isActive: 'Série',
          nome: "Elite histórias breves: Omar, Ander e Alexis"
        },
        {
          isActive: 'Série',
          nome: "Elite histórias breves: Patrick"
        },
        {
          isActive: 'Série',
          nome: "Elite histórias breves: Phillipe, Caue e Felipe"
        },
        {
          isActive: 'Série',
          nome: "Elite histórias breves: Samuel e Omar"
        },
        {
          isActive: 'Série',
          nome: "Elize matsunaga..."
        },
        {
          isActive: 'Série',
          nome: "Emily em Paris"
        },
        {
          isActive: 'Série',
          nome: "Eu odeio natal – (12/12)"
        },
        {
          isActive: 'Série',
          nome: "Fate: a saga winx"
        },
        {
          isActive: 'Série',
          nome: "Fearless: 8 segundos para a glória"
        },
        {
          isActive: 'Série',
          nome: "Ginny e georgia"
        },
        {
          isActive: 'Série',
          nome: "Glória"
        },
        {
          isActive: 'Série',
          nome: "Guardiões da floresta"
        },
        {
          isActive: 'Série',
          nome: "Guardiões da mansão do terror"
        },
        {
          isActive: 'Série',
          nome: "Half bad: o filho bastardo do diabo"
        },
        {
          isActive: 'Série',
          nome: "Ideias à venda"
        },
        {
          isActive: 'Série',
          nome: "Irmandade – br"
        },
        {
          isActive: 'Série',
          nome: "Iron chef Brasil – br"
        },
        {
          isActive: 'Série',
          nome: "João de deus: cura e crime – br"
        },
        {
          isActive: 'Série',
          nome: "La casa de papel"
        },
        {
          isActive: 'Série',
          nome: "La casa de papel: de Tóquio a Berlim"
        },
        {
          isActive: 'Série',
          nome: "La casa de papel: el fenómeno"
        },
        {
          isActive: 'Série',
          nome: "Lugar de mulher"
        },
        {
          isActive: 'Série',
          nome: "Lupin"
        },
        {
          isActive: 'Série',
          nome: "Maldivas"
        },
        {
          isActive: 'Série',
          nome: "Meu amor: seis histórias de amor verdadeiro"
        },
        {
          isActive: 'Série',
          nome: "Meu encontro com mal"
        },
        {
          isActive: 'Série',
          nome: "Mundo mistério"
        },
        {
          isActive: 'Série',
          nome: "Nada suspeitos – br"
        },
        {
          isActive: 'Série',
          nome: "Nasce uma rainha"
        },
        {
          isActive: 'Série',
          nome: "Neymar: o caos perfeito – br"
        },
        {
          isActive: 'Série',
          nome: "Ninguém tá olhando -br"
        },
        {
          isActive: 'Série',
          nome: "O cangaceiro do futuro (12/01)"
        },
        {
          isActive: 'Série',
          nome: "O clube da meia noite"
        },
        {
          isActive: 'Série',
          nome: "O crush perfeito"
        },
        {
          isActive: 'Série',
          nome: "O curioso mundo de james"
        },
        {
          isActive: 'Série',
          nome: "O escolhido"
        },
        {
          isActive: 'Série',
          nome: "O gabinete de curiosidades: de Guilherme del toro – (12/12)"
        },
        {
          isActive: 'Série',
          nome: "O mecanismo"
        },
        {
          isActive: 'Série',
          nome: "O menino maluquinho – br"
        },
        {
          isActive: 'Série',
          nome: "Olhar indiscreto (12/01)"
        },
        {
          isActive: 'Série',
          nome: "Ollie, o coelhinho perdido"
        },
        {
          isActive: 'Série',
          nome: "Oni: a lenda do deus do trovão"
        },
        {
          isActive: 'Série',
          nome: "Onisciente"
        },
        {
          isActive: 'Série',
          nome: "Os irregulares de Laker Street"
        },
        {
          isActive: 'Série',
          nome: "Pacto de sangue"
        },
        {
          isActive: 'Série',
          nome: "Patrulheiro em ação"
        },
        {
          isActive: 'Série',
          nome: "Por trás de seus olhos"
        },
        {
          isActive: 'Série',
          nome: "Queer eye Brasil – br"
        },
        {
          isActive: 'Série',
          nome: "Realityz"
        },
        {
          isActive: 'Série',
          nome: "Recomeço"
        },
        {
          isActive: 'Série',
          nome: "Recruta (12/01)"
        },
        {
          isActive: 'Série',
          nome: "Residente evil: a série"
        },
        {
          isActive: 'Série',
          nome: "Respire!"
        },
        {
          isActive: 'Série',
          nome: "Roubos inacreditáveis"
        },
        {
          isActive: 'Série',
          nome: "Round 6"
        },
        {
          isActive: 'Série',
          nome: "Samantha!"
        },
        {
          isActive: 'Série',
          nome: "Sandman"
        },
        {
          isActive: 'Série',
          nome: "Santo – br"
        },
        {
          isActive: 'Série',
          nome: "Sexify"
        },
        {
          isActive: 'Série',
          nome: "Sexlife (+18 adulto)"
        },
        {
          isActive: 'Série',
          nome: "Sintonia"
        },
        {
          isActive: 'Série',
          nome: "Só se for por amor – br "
        },
        {
          isActive: 'Série',
          nome: "Sonic prime (12/01)"
        },
        {
          isActive: 'Série',
          nome: "Spectros"
        },
        {
          isActive: 'Série',
          nome: "Street food: américa latina"
        },
        {
          isActive: 'Série',
          nome: "Super drags: só para adultos, querida!"
        },
        {
          isActive: 'Série',
          nome: "Temporada de verão"
        },
        {
          isActive: 'Série',
          nome: "The circle Brasil: o reality - br"
        },
        {
          isActive: 'Série',
          nome: "The fabulous (12/01)"
        },
        {
          isActive: 'Série',
          nome: "The witcher: a origem (12/01)"
        },
        {
          isActive: 'Série',
          nome: "Três vezes paixão"
        },
        {
          isActive: 'Série',
          nome: "Tubarão"
        },
        {
          isActive: 'Série',
          nome: "Vai Anitta"
        },
        {
          isActive: 'Série',
          nome: "Wandinha"
        },
        {
          isActive: 'Série',
          nome: "Arvolandia (23/01)"
        },
        {
          isActive: 'Suspense',
          nome: "Bird Box"
        },
        {
          isActive: 'Suspense',
          nome: "Escolha ou morra"
        },
        {
          isActive: 'Suspense',
          nome: "Fim da estrada"
        },
        {
          isActive: 'Suspense',
          nome: "Fuja"
        },
        {
          isActive: 'Suspense',
          nome: "O enfermeiro da noite"
        },
        {
          isActive: 'Suspense',
          nome: "O pálido olho azul"
        },
        {
          isActive: 'Suspense',
          nome: "O perfumista"
        },
        {
          isActive: 'Suspense',
          nome: "Passei por aqui"
        },
        {
          isActive: 'Suspense',
          nome: "Spiderhead"
        },
        {
          isActive: 'Terror',
          nome: "Army of the dead: invasão em Las Vegas"
        },
        {
          isActive: 'Terror',
          nome: "Escolha ou morra"
        },
        {
          isActive: 'Terror',
          nome: "Exterminadores do além: contra a loira do banheiro"
        },
        {
          isActive: 'Terror',
          nome: "Fuja"
        },
        {
          isActive: 'Terror',
          nome: "Lar dos esquecidos"
        },
        {
          isActive: 'Terror',
          nome: "O monastério"
        },
        {
          isActive: 'Terror',
          nome: "Tem alguém na sua casa"
        },
        {
          isActive: 'Terror',
          nome: "Terapia do medo"
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
        { value: "Documentário", text: "Documentário" },
        { value: "Drama", text: "Drama" },
        { value: "Estrangeiros", text: "Estrangeiros" },
        { value: "Ficção e fantasia", text: "Ficção e fantasia" },
        { value: "Música e musicais", text: "Música e musicais" },
        { value: "Para a família toda", text: "Para a família toda" },
        { value: "Romance", text: "Romance" },
        { value: "Série", text: "Série" },
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
.search {
  display: flex;
  gap: 10px;
  align-items: center;
  justify-content: center;
  margin: 10px;
}

.tabelaCor {
  color: white !important;
}

.tabelaMain {
  max-width: 100%;
}

.colorInput,
.colorSelect {
  color: #f8f9fa !important;
  background: #212529 !important;
  border-radius: 5px;
  padding: .6em;
}

.table-striped>tbody>tr:nth-of-type(odd)>* {
  color: white !important;
}

.colorInput {
  width: 10em !important;
}

@media only screen and (max-width: 599px) {
  .search {
    display: flex;
    gap: 10px;
    align-items: center;
    justify-content: center;
    margin: 10px;
    flex-direction: column;
  }

  .colorInput,
  .colorSelect {
    width: auto !important;
  }
}

@media only screen and (min-width: 768px) {
  .tabelaCor {
    width: auto !important;
  }
}
</style>
