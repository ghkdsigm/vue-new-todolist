<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo" placeholder="할일을적어죠" />
    <span class="addContainer"  v-on:click="addTodo">
      <i class="fas fa-plus addBtn"></i>
    </span>

    <Modal v-if="showModal" @close="showModal = false">
        <!--
            you can use custom content here to overwrite
            default content
        -->
      <h3 slot="header">경고!!</h3>
      <h3 slot="body">일정을 입력하세요</h3>
      <h3 slot="footer">
         <button class="modal-default-button" @click="showModal = false">
          OK
        </button> 
      </h3>
    </Modal>
  </div>
</template>

<script>
import Modal from './common/Modal.vue'
export default {
  data: function(){
    return{
      newTodoItem:"",
      showModal:false
    }
  },
  methods:{
    addTodo: function(){
      if(this.newTodoItem !== ''){
        //this.$emit('addTodoItem', this.newTodoItem)
        this.$store.commit('addOneItem', this.newTodoItem);
        this.clearInput();
      } else {
        this.showModal =!this.showModal
      }
    },
    
    clearInput:function(){
      this.newTodoItem = '';
    }
  },
  components:{
    Modal: Modal
  }
}
</script>

<style scoped>
input:focus {
  outline: none;
}
.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
  position: relative;
  margin:0 10px;
}
.inputBox input {
  border-style: none;
  font-size: 0.9rem;
  width: 90%;
  position: relative;
  left: 0;
  display: inline-block;
}
.addContainer {
  float: right;
  background: linear-gradient(to right, #62EAC6, #32CEE6);
  display: block;
  width: 3rem;
  border-radius: 0 5px 5px 0;   
  position: absolute;
  right: 0;
  top: 0;
}
.addBtn {
  color: white;
  vertical-align: middle;
}
</style>
