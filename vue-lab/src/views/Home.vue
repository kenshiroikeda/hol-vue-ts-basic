<template>
  <div class="home">
    <h3>テキストバインディング</h3>
    <span>{{ computedMsg }}</span>
    <h3>リストレンダリング</h3>    
    <ul id="item-list">
      <li v-for="item in items" :key="item.id">
        {{item.name}}
      </li>
    </ul>
    <h3>イベントハンドリング</h3>
    <button v-on:click="onClick">実行</button>
    <h3>条件付きハンドリング</h3>
    <button v-on:click="showDetail">表示</button>
    <div v-if="detail">
      詳細が表示されました。
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

declare interface Item {
  id:number;
  name:string;
}

export default Vue.extend({
  data() {
    return {
      msg: "Hello Vue.js!",
      detail: false,
      items: [
        {
          id: 1,
          name: "keyboard"
        },
        {
          id: 2,
          name: "mouse"
        }
      ] as Item[]
    }
  },
  computed: {
    computedMsg():String {
      return this.msg.replace(/!/g, "") + " + TypeScript!";
    }
  },
  methods: {
    onClick(): void{
      alert(this.msg);
    },
    showDetail():void{
      this.detail = true;
    }
  }
});
</script>

<style scoped>
.home {
  text-align: left;
}
</style>