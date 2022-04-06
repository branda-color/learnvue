<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
      <input type="text" v-model="text">
    <p>{{text}}</p>
    <button v-on:click="addnum">ADD</button>
    <p>{{num}}</p>
    <!-- 綁定鍵盤enter按下去談上來的瞬間 -->
    <input type="text" v-model="text2" @keyup.enter="addtask"><button @click="addtask">Submit</button>
    <p v-for="(task,index) in todo_list" v-bind:key="task">
      {{index}}{{task}}
    </p>
    <ul>
        <!-- bind-key是為了在dom上面有id綁定才可以顯示 -->
        <li v-for="(todo,index) in todos" v-bind:key="index">
            <label>{{todo.value}}</label>
            <label >{{todo.done}}</label>
        </li>
    </ul>
</template>


<script>
export default {
    name:'Test-item',
    data(){
        return {
            text:"helloworld",
            num:0,
            todo_list:[],
            text2:"",
            todos:[
                {value:"關於vue",done:false},
                {value:"關於vue2",done:true},
                {value:"關於vue3",done:false}
            ]
        }
    },
    methods:{
        addnum(){
            this.num+=1
        }
        ,addtask(){
            this.todo_list.push(this.text2)
            this.text2=""
        }
    }
}
</script>

<style lang='less'>
@import'../assets/todos.less';
</style>
