<template>
  <div class="clearAllContainer">
    <span class="clearAllBtn" v-on:click="clearTodo">전체삭제</span>
  </div>
</template>

<script>
import {mapMutations } from 'vuex'
export default {
  methods: {
    ...mapMutations({
      clearTodo: 'clearAllItems'
    })     
  }, 
}
</script>

<style scoped>
.clearAllContainer{
  width:8.5rem;
  height:30px;
  line-height: 30px;
  background-color:#ebebeb;
  border-radius: 5px;
  margin:0 auto;
}
.clearAllBtn {
  color:#ff2600;
  display:block;
  margin-top:25px;
  cursor: pointer;
    font-size: 13px;
}
.clearAllContainer:hover {
  background:#ff2600;
}
.clearAllContainer:hover .clearAllBtn {
  color:#fff;
}
</style>
