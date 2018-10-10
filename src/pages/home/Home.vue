<template>
  <div>
    <div class="home">Home</div>
    <router-link to="/list" class="home">列表页</router-link>
  </div>

</template>
<script>
export default {
  name: 'Home'
}
</script>
<style>
  .home {
    font-size: 30px;
  }
</style>
