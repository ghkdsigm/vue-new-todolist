<template>
  <div class="clearAllContainer">
    <span class="clearAllBtn" v-on:click="clearTodo">Clear ALL</span>
  </div>
</template>

<script>
export default {
 methods:{   
   clearTodo : function(){
     this.$store.commit('clearAllItems')
   }   
 }
}
</script>

<style scoped>
.clearAllContainer{
  width:8.5rem;
  height:50px;
  line-height: 50px;
  background-color:#fff;
  border-radius: 5px;
  margin:0 auto;
}
.clearAllBtn {
  color:#ff2600;
  display:block;
  margin-top:25px;
  cursor: pointer;
}
.clearAllContainer:hover {
  background:#ff2600;
}
.clearAllContainer:hover .clearAllBtn {
  color:#fff;
}
</style>
