<template>
  <div>
    <h1>Tab with posts</h1>
    <my-input
        v-focus
        v-model="searchQuery"
        placeholder="Search"
    />
    <div class="app__btns">
      <my-button
      >
        Create post
      </my-button>
      <my-select
          v-model="selectedSort"
          :options="sortOptions"
      />
    </div>
    <my-dialog v-model:show="dialogVisible">
      <post-form
      />
    </my-dialog>
    <post-list
        :posts="sortedAndSearchedPosts"
        v-if="!isPostsLoading"
    />
    <div v-else>Loading...</div>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
import MySelect from "@/components/UI/MySelect";
import MyPageWrapper from "@/components/UI/MyPageWrapper";
import {usePosts} from "@/hooks/usePosts";
import useSortedPosts from "@/hooks/useSortedPosts";
import useSortedAndSearchedPosts from "@/hooks/useSortedAndSearchedPosts";

export default {
  components: {
    MySelect,
    PostList,
    PostForm,
    MyPageWrapper,
  },
  data() {
    return {
      dialogVisible: false,
      sortOptions: [
        {value: 'title', name: 'by title'},
        {value: 'body', name: 'by body'},
      ]
    }
  },
  setup(props) {
    const {posts, totalPages, isPostsLoading} = usePosts(10);
    const {sortedPosts, selectedSort} = useSortedPosts(posts);
    const {searchQuery, sortedAndSearchedPosts} = useSortedAndSearchedPosts(sortedPosts)
    return {
      posts,
      totalPages,
      isPostsLoading,
      sortedPosts,
      selectedSort,
      searchQuery,
      sortedAndSearchedPosts,
    }
  }
}
</script>

<style>


.app__btns {
  display: flex;
  justify-content: space-between;
  margin: 15px 0;
}

.observer {
  height: 30px;
}

</style>