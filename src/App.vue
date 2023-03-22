<template>
  <div class="app">
    <form @submit.prevent>
      <p>create a title</p>
      <input v-bind:value="title"
             @input="title=$event.target.value"
             class="input"
             type="text"
             placeholder="Name">
      <input v-bind:value="body"
             @input="body=$event.target.value"
             class="input"
             type="text"
             placeholder="Description">
      <button class="btn"
              @click="createPost"
      >
        create
      </button>
    </form>
    <div class="post" v-for="post in posts">
      <div><strong>Name</strong>{{ post.title }}</div>
      <div><strong>Description</strong>{{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: "JavaScript", body: "description"},
        {id: 2, title: "JavaScript 2", body: "description 2"},
        {id: 3, title: "JavaScript 3", body: "description 3"},
      ],
      title: "",
      body: ""
    }
  },
  methods: {
    createPost(event) {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body
      }
      this.posts.push(newPost)
      this.title = ""
      this.body = ""
    },
    // inputTitle(event){
    //   this.title = event.target.value
    // }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  margin: 15px;
}

.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}

form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}

</style>

