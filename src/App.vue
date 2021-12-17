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
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";

export default {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'JS1', body: 'DS1'},
        {id: 2, title: 'JS2', body: 'DS2'},
        {id: 3, title: 'JS3', body: 'DS3'},
        {id: 4, title: 'JS4', body: 'DS4'},
      ],
    }
  },
  methods: {
    createPost(newPost) {
      this.posts.push(newPost);
    }
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
  padding: 20px;
}


</style>