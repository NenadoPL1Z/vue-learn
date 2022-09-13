<template>
  <form class="add-post" @submit.prevent>
    <h1>Create post</h1>
    <br/>
    <div class="input-container">
      <input
          v-model="post.title"
          class="input"
          type="text"
          placeholder="title"
      />
    </div>
    <div class="input-container">
      <input
          :value="post.body"
          @input="post.body = $event.target.value"
          class="input"
          type="text"
          placeholder="desc"
      />
    </div>
    <button class="button" type="submit" @click="handleCreatePost">add new post</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    }
  },
  methods: {
    handleCreatePost() {
      this.post.id = Date.now();
      this.$emit("create", this.post)
      this.post = {
        title: "",
        body: "",
      }
    }
  }
}
</script>

<style scoped>
.add-post {
  margin-bottom: 20px;
}
.input-container {
  margin-bottom: 20px;
}
.input {
  display: block;
  padding: 10px 20px;
  width: 100%;
  border-radius: 10px;
  border: 1px solid lightseagreen;
}
.button {
  border: 0;
  cursor: pointer;
  border-radius: 10px;
  color: #2c2c2c;
  padding: 10px 20px;
  text-transform: uppercase;
  background-color: lightseagreen;
}
</style>
