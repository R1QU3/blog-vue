<template>
  <div class="artigo-container">
    <h1 class="artigo-title">
      {{ title }}
    </h1>
    <p class="artigo-content">
      {{ content }}
    </p>
  </div>
</template>
<script>
export default {
  name: 'ArtigoCard',
  props: {
    title: String,
    content: String,
  }
}
</script>
<style scoped>
  
.artigo-container {
  max-width: 600px;
  margin: 1rem auto;
  text-align: left;
  padding: .775rem;
  border-radius: 5px;
  background: #303030;
}

.artigo-title {
  font-size: 1.8rem;
}

.artigo-content {
  color: #ccc;
}

</style>