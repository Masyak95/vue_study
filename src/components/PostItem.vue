<template>
  <div class="post">
    <div>
      <div><strong>Name: </strong>{{ post.title }}</div>
      <div><strong>Description: </strong>{{ post.body }}</div>
    </div>
    <div class="post__btn">
      <my-button>delete</my-button>
    </div>
  </div>

</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";

export default {
  components: {MyButton},
  props:{
    post:{
      type: Object,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>