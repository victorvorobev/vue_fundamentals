<template>
  <button class="btn">
    <slot>
      <!-- Default slot for text on the button -->
    </slot>
  </button>
</template>

<script>
export default {
  name: "my-button"
}
</script>

<style scoped>
.btn {
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>