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
        <!-- 1 - A LINHA A SEGUIR MOSTRA QUE É POSSÍVEL APLICAR ESTILO NO ESCOPO DO COMPONENT FILHO MESMO ESTANDO NO ESCOPO DO COMPONENT PAI -->

        <p class="estilo-filho-no-pai">1) Um slot sem o atributo "name" é um slot padrão</p>

        <!-- 2 - JÁ A LINHA A SEGUIR MOSTRA UMA ESTILIZAÇÃO DEFINIDA NO ESCOPO DO COMPONENTE FILHO APLICADA AO COMPONENT FILHO MESMO ESSE COMPONENT FILHO ESTANDO NO ESCOPO DO COMPONENT PAI-->
        <p class="estilo-filho-no-filho">2 ) Um slot padrão recebe todo e qualquer elemento HTML dentro do Component que não faça referência a um slot nomeado<p>
        <p>3) Se um slot tiver o atributo name, porém ele estiver vazio, ele não recebe conteúdos</p>
        <span>...</span>
      </template>
      <!-- 3 - CONCLUSÃO, A REGRA GERAL É SIMPLES, CADA ELEMENTO VAI COMPILAR COM O SEU PRÓPRIO ESCOPO -->

      <small slot="rodape">{{ autor }}</small>
      <template slot="botao">Detalhes</template>
    </Post>
  </div>
</template>

<script>

import Post from './components/Post.vue'

export default {
  components: {
    Post
  },
  data () {
    return {
      autor: 'Plínio Naves'
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
