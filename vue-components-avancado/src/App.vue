<template>
  <div id="app" class="container">
    <div>
       <div class="topo"><img src="./imagens/vue-icon.png"></div>
       <div class=""><h1>Vue JS</h1></div>
    </div>

    <h1>Forma padrão</h1>
    <PostsLista :posts="posts"/>

    <hr>

    <h1>Slost com Escopo</h1>
    <PostsLista :posts="posts">
      <template slot-scope="slotProps">
        <h2 style="color:blue">{{ slotProps.meuPost.titulo }}</h2>
        <p> {{ slotProps.meuPost.conteudo }} </p>
        <small> {{slotProps.meuPost.autor }} </small>
      </template>
    </PostsLista>

    <PostsLista :posts="posts">
      <template slot-scope="slotProps">
        <h2 style="color:red">{{ slotProps.meuPost.titulo }}</h2>
        <p> {{ slotProps.meuPost.conteudo }} </p>
        <small> {{slotProps.meuPost.autor }} </small>
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
      posts: [
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
