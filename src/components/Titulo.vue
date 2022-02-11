<template>
  <h1>{{ text }}</h1>
</template>
<script>
export default {
  name: 'Titulo',
  props: {
    text: String,
  }
}
</script>
<style scoped>
h1 {
  margin-top: 1.5rem;
  margin-bottom: 1.5rem;
}
</style>