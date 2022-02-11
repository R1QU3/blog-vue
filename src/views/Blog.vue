<template>
    <Titulo text="Blog"/>
    <div class="blogs" v-for="item in arrayBlog" :key="item.id">
      <router-link class="post-link" :to="`/blog/${item.id}`">
        {{item.title}}
      </router-link>
    </div>
</template>
<script>

import Titulo from '@/components/Titulo.vue'

export default {
  name: 'Blog',
  components: {
    Titulo,
  },
  data() {
    return {
      arrayBlog: [],
    }
  },
  methods: {
    async consumirAPI() {
      try {
        const data = await fetch('https://jsonplaceholder.typicode.com/posts')
        const array = await data.json()
        this.arrayBlog = array
        console.log(this.arrayBlog)
      } catch (error) {
        console.log(error)
      }
    },
  },
  created() {
    this.consumirAPI()
  }
}
</script>
<style scoped>
.blogs{
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  text-align: left;
  max-width: 600px;
  margin: 1rem auto;
}

.post-link {
  text-decoration: none;
  color: #af8;
  background: #007542;
  border-radius: 5px;
  padding: 1rem;
  transition: all .3s ease-in-out;
}
.post-link:hover {
  text-decoration: underline;
  transform: scale(1.05);
  box-shadow: 0px 0px 10px 1px #af8;
}

</style>