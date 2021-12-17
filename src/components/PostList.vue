<template>
  <div>
    <h3>Posts from users</h3>
    <post-item
        v-for="post in posts"
        :post="post"
    />
  </div>
</template>

<script>
import PostItem from "@/components/PostItem";

export default {
  components: {PostItem},
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>

</style>