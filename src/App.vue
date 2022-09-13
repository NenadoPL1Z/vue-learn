<template>
  <post-form @create="handleCreatePost"/>
  <post-list :posts="posts"/>
</template>

<script>
import PostList from "@/components/PostList";
import PostForm from "@/components/PostForm";
export default {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        {id: 1, title: "Post 1", body: "Desc 1"},
        {id: 2, title: "Post 2", body: "Desc 2"},
        {id: 3, title: "Post 3", body: "Desc 3"},
        {id: 4, title: "Post 4", body: "Desc 5"},
      ]
    }
  },
  methods: {
    handleCreatePost(newPostObj) {
      this.posts.push(newPostObj);
    }
  }
}
</script>

<style>
  body {
    background-color: #2c2c2c;
    color: white;
    padding: 20px
  }
  *, *:after, *:before {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
</style>
