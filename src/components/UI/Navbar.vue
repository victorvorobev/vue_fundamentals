<template>
  <div class="navbar">
    <div @click="$router.push('/')">VUE3 fundamentals</div>
    <div class="navbar__btns">
      <my-button @click="$router.push('/posts')">Posts</my-button>
      <my-button style="margin-left: 20px" @click="$router.push('/about')">About</my-button>
      <my-button style="margin-left: 20px" @click="$router.push('/store')">Posts with store</my-button>
      <my-button style="margin-left: 20px" @click="$router.push('/composition')">Posts with composition</my-button>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.navbar {
  height: 50px;
  background-color: lightgrey;
  box-shadow: 2px 2px 4px gray;
  display: flex;
  align-items: center;
  padding: 0 15px;
}

.navbar__btns {
  margin-left: auto;
}
</style>