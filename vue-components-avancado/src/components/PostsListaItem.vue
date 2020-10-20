<template>
    <div class="post">
        <!-- ESSE COMPONENT VAI FUNCIONAR COMO UM MODELO DE TUPLA/OCORRENCIA/REGISTRO -->
        <slot>
            <div class="post-cabecalho">
                <h2>{{ ocorrencia.titulo }}</h2>
            </div>

                <div class="post-conteudo">
                   <p>{{ ocorrencia.conteudo }}</p>
                </div>

                <div class="post-rodape">
                    <small>{{ ocorrencia.autor }}</small>
                        <a href="#" class="link">Ler mais ...</a>
            </div>
        </slot>

    </div>
</template>

<script>
export default {
  props: {
    ocorrencia: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>

    .post {
        margin: 15px auto;
    }

    .post-cabecalho {
        padding: 5px 12px;
        background: #eee;
    }

    .post-conteudo {
        background: rgb(146, 133, 160);
        padding: 15px;
        font-size: 16px;
    }

    .post-rodape {
        font-style: italic;
    }

    .link {
        float: right;
    }

    .estilo-filho-no-filho {
        color: yellow;
    }
</style>
