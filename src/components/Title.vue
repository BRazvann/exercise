<template>
  <div class="title">
    <h1>
      <img alt="logo" src="../assets/logo.png">
      {{ msg }}
    </h1>
  </div>
</template>

<script>
export default {
  name: 'Title',
  props: {
    msg: String
  }
}
</script>

<style scoped>
img {
  vertical-align: middle;
}
</style>
