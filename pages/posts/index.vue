<template>
  <ul class="posts">
    <li class="posts__post" v-for="post in posts" :key="post.id">
      <nuxt-link :to="{name: 'posts-id', params:{id: post.id}}">{{post.title}}</nuxt-link>
    </li>
  </ul>
</template>

<script>
  export default {
    name: "posts ",
    head() {
      return {
        title: 'List of Posts'
      }
    },
    data() {
      return {}
    },
    computed: {
      posts() {
        return this.$store.state.posts.all;
      }
    }
  }
</script>

<style scoped>

</style>
