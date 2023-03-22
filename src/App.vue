<template>
  <div class="app">
    <post-form
        @create="createPost"
    />
    <post-list
        :posts="posts"


    />

  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue"
import PostList from "@/components/PostList.vue"



export default {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        {id: 1, title: "JavaScript ", body: "description"},
        {id: 2, title: "JavaScript 2 ", body: "description 2"},
        {id: 3, title: "JavaScript 3 ", body: "description 3"},
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    }
  }
}
</script>

<style >
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  margin: 15px;
}

form {
  display: flex;
  flex-direction: column;
}


</style>

