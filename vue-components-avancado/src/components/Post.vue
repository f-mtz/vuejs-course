<template>
    <div class="post">

        <div class="post-cabecalho">
            <slot name="cabecalho"></slot>
        </div>

        <div class="post-conteudo">
            <slot></slot>
        </div>

        <div class="post-rodape">
            <slot name="rodape"></slot>
            <!-- Conteúdos Default -->
            <!-- Caso não seja passado conteúdo ele se mantêm, se for passado conteúdo ele será substituído -->
            <a href="#" class="link">
                <slot name="botao">Saiba mais...</slot>
            </a>
        </div>
    </div>
</template>

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
