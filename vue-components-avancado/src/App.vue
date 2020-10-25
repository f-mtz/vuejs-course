<template>
  <div id="app" class="container">
    <h1>Components Dinâmicos</h1>
    <button @click="componentSelecionado = 'Home'">Home</button>
    <button @click="componentSelecionado = 'PostsLista'">Posts</button>
    <button @click="componentSelecionado = 'Sobre'">Sobre</button>

    <p> {{ componentSelecionado }} </p>
    <component :is="componentSelecionado"></component>
  </div>
</template>

<script>
import Home from './components/Home.vue'
import PostsLista from './components/PostsLista.vue'
import Sobre from './components/Sobre.vue'

export default {
  components: {
    Home,
    PostsLista,
    Sobre
  },
  data () {
    return {
      componentSelecionado: 'Home',
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
