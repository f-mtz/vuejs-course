<template>
  <div id="app" class="container">
    <div>
       <div class="topo"><img src="./imagens/vue-icon.png"></div>
       <div class=""><h1>Vue JS</h1></div>
    </div>

    <h1>Forma padrão:</h1>
    <PostsLista :posts="objs"/>
    <!-- AQUI OS COMPONENTS FILHOS SERÃO RENDERIZADOS E ESTILIZADOS DE FORMA CUSTOMIZADA -->
    <hr>

    <h1>Slost com Escopo:</h1>
    <PostsLista :posts="objs">
      <template slot-scope="{ conteudo }">
        <h2 style="color:blue">{{ conteudo.titulo }}</h2>
        <p> {{ conteudo.conteudo }} </p>
        <small> {{conteudo.autor }} </small>
      </template>
    </PostsLista>

    <PostsLista :posts="objs">
      <template slot-scope="slotProps">
        <h2 style="color:red">{{ slotProps.conteudo.titulo }}</h2>
        <p> {{ slotProps.conteudo.conteudo }} </p>
        <small> {{slotProps.conteudo.autor }} </small>
      </template>
    </PostsLista>
  <!-- RESUMO DA AULA:

       O CONCEITO DE SLOTS COM ESCOPO É IMPORTANTE POIS PERMITE POR EXEMPLO IMPLEMENTAR LAYOUTS CUSTOMIZADOS E REUTILIZÁVEIS POPULADOS PELA APLICAÇÃO
  -->
  </div>
</template>

<script>
import PostsLista from './components/PostsLista.vue'

export default {
  components: {
    PostsLista
  },
  data () {
    return {
      objs: [
        { id: 1, titulo: 'Components no Vue', conteudo: 'Components são uma das peças mais importantes no Vue', autor: 'Plinio Naves' },
        { id: 2, titulo: 'Distribuindo conteúdos com slots', conteudo: 'Slots podem ser usados como repositórios de código HTML', autor: 'Plinio Naves' }

      ]
    }
  }
}
</script>

<style scoped>
  .container {
    width: 960px;
    margin: auto;
  }

  img {
    width: 45px;
  }

  .topo {
    float: left;
  }

  .estilo-filho-no-pai {
    color: white;
  }

</style>
