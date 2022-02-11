<template>
  <div class="comentary">
    <h2 class="name">
      {{ name }}
    </h2>
    <a class="email" href="#">
      {{ email }}
    </a>
    <p class="content">
      {{ content }}
    </p>
  </div>
</template>
<script>
export default {
  name: 'Comentary',
  props: {
    name: String,
    email: String,
    content: String,
  }
}
</script>
<style scoped>

.comentary {
  max-width: 600px;
  margin: 1rem auto;
  text-align: left;
  padding: .775rem;
  border-radius: 5px;
  background: #202020;
}

.name {
  margin: 0;
  font-size: 1.3rem;
}

.email {
  text-decoration: none;
  color: #2666CF;
  transition: all .3s;
}
.email:hover {
  color: #af8;
}
.content {
  color: #ccc;
  line-height: 1.1;
}

</style>