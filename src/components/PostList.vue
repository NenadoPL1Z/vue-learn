<template>
  <div class="post" v-for="post in posts" key="{{post.id}}}">
    <h1>Title: {{post.title}}</h1>
    <p>Description: {{post.body}}</p>
    <a href="/v1">open full page post:{{post.id}}</a>
  </div>
</template>

<script>
export default {
  props: {
    posts: {
      type: Array,
      required: true,
    }
  }
}
</script>

<style scoped>
  .post {
    padding: 20px 30px;
    border-radius: 10px;
    margin-bottom: 30px;
    box-shadow: 0 0 5px lightseagreen;
  }
</style>
