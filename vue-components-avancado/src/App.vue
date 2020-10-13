<template>
  <div id="app" class="container">
    <div>
       <div class="topo"><img src="./imagens/vue-icon.png"></div>
       <div class=""><h1>Vue JS</h1></div>
    </div>
    <div></div>
    <Post>
      <h1 slot="cabecalho">Components no Vue</h1>
      <template slot="">
        <p>1) Um slot sem o atributo "name" é um slot padrão</p>
        <p>2) Um slot padrão recebe todo e qualquer elemento HTML dentro do Component que não faça referência a um slot nomeado<p>
        <p>3) Se um slot tiver o atributo name, porém ele estiver vazio, ele não recebe conteúdos</p>
        <span>...</span>
      </template>
      <small slot="rodape">by: Plínio Naves</small>
      <template slot="botao">Detalhes</template>
    </Post>
  </div>
</template>

<script>

import Post from './components/Post.vue'
export default {
  components: {
    Post
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
</style>
