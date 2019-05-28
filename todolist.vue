<template>
  <div class="box">
    <input type="text" v-model="inputvalue">
    <button @click="handsubmit">提交</button>
    <ul>
      <todo-item v-for="(item, index) of list" :key="index" :content="item" :index="index" @delete="handdelete"></todo-item>
    </ul>
  </div>
</template>

<script>
  import todoitem from './components/todoitem'  //接收子组件
	export default{
    components:{
      'todo-item':todoitem   //声明组件
    },
		data(){
      return{
        inputvalue:'',
        list:[]
      }
    },
    methods:{
      handsubmit(){
        this.list.push(this.inputvalue)
        this.inputvalue=''
      },
      handdelete(index){
        this.list.splice(index,1)
      }
    }
	}
</script>

<style>
  input{
    width: 200px;
    height: 30px;
    border-radius: 2px;
    outline: none;
    border: 1px solid rgb(224, 224, 224);
    color: red;
    padding-left: 5px;
  }
  button{
    width: 60px;
    height: 30px;
    border: 1px solid #5FB878;
    color: #fff;
    background: #5FB878;
    border-radius: 3px;
    outline: none;
    cursor: pointer;
    margin-left: 3px;
  }
  ul{
    list-style-type: none;
  }
</style>
