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
</template>


<script>
export default {
    name:'Test-item',
    data(){
        return {
            text:"helloworld",
            num:0,
            todo_list:[],
            text2:""
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

<style>

</style>
