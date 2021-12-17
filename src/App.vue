<template>
  <div class="app">
    <h1>Tab with posts</h1>
    <my-button
        style="margin: 15px 0;"
        @click="showDialog"
    >
      Create post
    </my-button>
    <my-dialog v-model:show="dialogVisible">
      <post-form
          @create="createPost"
      />
    </my-dialog>
    <post-list
        :posts="posts"
        @remove="removePost"
    />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";

export default {
  components: {
    PostList,
    PostForm,
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'JS1', body: 'DS1'},
        {id: 2, title: 'JS2', body: 'DS2'},
        {id: 3, title: 'JS3', body: 'DS3'},
        {id: 4, title: 'JS4', body: 'DS4'},
      ],
      dialogVisible: false,
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    },
    showDialog() {
      this.dialogVisible = true;
    },
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