<template>

  <div>
    <post-item
        v-for="post in posts"
        :post="post"
    />
  </div>

</template>

<script>
 import PostItem from "@/components/PostItem.vue";

 export default {
   components: {PostItem},
  props:{
    posts:{
      type: Array,
      required: true
    }
  }

}
</script>

<style lang="scss" scoped>

</style>