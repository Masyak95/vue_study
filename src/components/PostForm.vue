<template>
  <form @submit.prevent>
    <p>create a title</p>

    <input v-model="post.title"
           class="input"
           type="text"
           placeholder="Name"
    >

    <input v-model="post.body"
           class="input"
           type="text"
           placeholder="Description"
    >

    <my-button class="btn"
               style="align-self: flex-end; margin-top: 15px"
               @click="createPost"
    >
      create
    </my-button>
  </form>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";

export default {
  components: {MyButton},
  data() {
    return {
      post: {
        title: "",
        body: "",
      }
    }
  },
  methods: {
    createPost(event) {
      this.post.id = Date.now()
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

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

</style>