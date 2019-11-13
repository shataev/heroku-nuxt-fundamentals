<template>
    <nav class="nav">
      <div class="logo">
        <a href="/" class="logo text-lg">
          Nuxt Fundamentals
        </a>
        <nuxt-link :to="{name: 'index'}">Nuxt Fundamentals</nuxt-link>
        <nuxt-link :to="{name: 'posts'}">Posts</nuxt-link>



      </div>
    </nav>
</template>

<script>
    export default {
        name: "navbar"
    }
</script>

<style scoped>

</style>
