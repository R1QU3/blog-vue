<template>
  <router-link class="back-btn" to="/blog">« Back</router-link>
  <ArtigoCard :title="`${arrayArtigo.title}`" :content="`${arrayArtigo.body}`"/>
  <section class="section-comentary">
    <Titulo text="Comments"/>
    <Comentary v-for="item in arrayComentary" :key="item.id"
     :name="item.name" 
     :email="item.email" 
     :content="item.body"/>
  </section>
</template>
<script>

// import
import Titulo from '@/components/Titulo.vue'
import ArtigoCard from '@/components/ArtigoCard.vue'
import Comentary from '@/components/Comentary.vue'

export default {
  name: 'Artigo',
  data() {
    return {
      arrayArtigo: [],
      arrayComentary: [],
    }
  },
  components: {
    ArtigoCard,
    Comentary,
    Titulo
  },
  methods: {
    async consumirArtigo() {
      try {
        const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
        const array = await data.json()
        this.arrayArtigo = array
        console.log(this.arrayArtigo)
      } catch (error) {
        console.log(error)
      }
    },
    async consumirComments() {
      try {
        const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}/comments`)
        const array = await data.json()
        this.arrayComentary = array;
        console.log(this.arrayComentary)
      } catch (error) {
        console.log(error)
      }
    }
  },
  created() {
    this.consumirArtigo()
    this.consumirComments()
  }
}
</script>
<style scoped>
.back-btn {
  display: inline-block;
  padding: .5rem 1rem;
  border-radius: 5px;
  text-decoration: none;
  font-weight: bold;
  background: #af8;
  color: #007542;
  transition: all .3s;
}
.back-btn:hover {
  transform: scale(1.1);
}
.section-comentary {
  text-align: left;
  margin: 0 auto;
  max-width: 600px;
  padding: .875rem;
  border-radius: 5px;
  background: #303030;
}
</style>