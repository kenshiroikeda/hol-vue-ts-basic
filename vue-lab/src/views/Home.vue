<template>
  <div class="home">
    <h3>テキストバインディング</h3>
    <span>{{ msg }}</span>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  data() {
    return {
      msg: "Hello Vue.js!"
    };
  }
});
</script>

<style scoped>
.home {
  text-align: left;
}
</style>