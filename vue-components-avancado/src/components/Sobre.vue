<template>
    <div>
        <h2>Sobre</h2>

        <p v-if="autor">Autor: {{ autor }}</p>
        <input type="text" v-model="autor">
        <!-- FICOU PROVADO ENTÃO DE 2 MANEIRAS QUE POR PADRÃO OS COMPONENTS DINÂMICOS CRIAM NOVAS INSTÂNCIAS
        AO ALTERNAR ENTRE OUTROS COMPONENTS -->
    </div>
</template>

<script>
export default {
  data () {
    return {
      autor: ''
    }
  },
  created () {
    console.log('Created!')
  },
  destroyed () {
    console.log('Destroyed!')
  },
  activated () {
    console.log('Esse Component está ativado')
  },
  deactivated () {
    console.log('Esse Component está desativado')
  }
}
</script>
