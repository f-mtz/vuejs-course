<template>
    <div>
        <h2>Lista de posts</h2>
        <!-- ESSE COMPONENT VAI SER RESPONSÁVEL POR RENDERIZAR A LISTA DE TUPLAS/OCORRENCIAS/REGISTROS -->
        <PostsListaItem
            v-for="ocorrencia in posts"
            :key="ocorrencia.id"
            :ocorrencia="ocorrencia">
                <slot :conteudo="ocorrencia"></slot>
        </PostsListaItem>
    </div>
</template>

<script>

import PostsListaItem from './PostsListaItem.vue'

export default {
  components: {
    PostsListaItem
  },
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>
