<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Titulo text="Looking for articles? Visit our blog :)"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Titulo from '@/components/Titulo.vue'

export default {
  name: 'Home',
  components: {
    Titulo,
  }
}
</script>
