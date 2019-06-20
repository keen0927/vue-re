

<template>
  <div id="app">
    <div id="header">
      <h2>할일</h2>
      <input 
        type="text"
        v-model.trim="todo"
        @keyup.enter="addTodo"
      >
      <button type="button" @click="addTodo">추가</button>
    </div>
    <ul id="totoList">
      <li 
        v-for="(a, index) in todoList"
        :class="checked(a.done)"
        @click="doneToggle(index)"
        :key="index"
      >
        <span>{{a.todo}}</span>
        <span v-if="a.done">(완료)</span>
        <span class="close" @click.stop="deleteTodo(index)">X</span>
      </li>
    </ul>
  </div>
</template>

<script>



export default {
  name: 'App',
  data: function(){
    return {
      todo: "",
      todoList: [
        {todo: "영화보기1", done:false},
        {todo: "영화보기2", done:false},
        {todo: "영화보기3", done:false},
        {todo: "영화보기4", done:false},
      ]
    }
  },
  methods: {
   checked: function(done) {
     if (done) return { checked: true};
     else return { checked: false}
   },
   addTodo: function(e) {
     console.log('addTodo');
     if (this.todo !== "") {
       this.todoList.push({ todo: this.todo, done: false});
       this.todo = "";
     }
   },
   deleteTodo: function(index) {
    //  this.todoList.slice(index,1);
    //  console.log('delete',index);
    this.todoList.splice(index, 1);
   },
   doneToggle: function(index) {
     this.todoList[index].done = !this.todoList[index].done;
   }
  },
  computed: {
    
  },
}
</script>

<style lang="scss">
.checked{
  color: gray
}
</style>
