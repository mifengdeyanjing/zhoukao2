<template>
  <div class="homebox">
      <h4>用户名:</h4>
      <input placeholder="输入用户名" v-model="name"/>
      <h4>年龄:</h4>
      <input placeholder="输入年龄" v-model="age"/>
        <br>
      <button class="tian" @click="add">添加</button>
      <button class="chong" @click="zhi">重置</button>
      <div class="xia">
        <Table :option="arr"/>
      </div>
  </div>
</template>

<script>
import Table from "./table"
export default {
    data(){
      return {
        name:"",
        age:"",
        arr:[],
        index:0,
        shan:"删除"
      }
    },
    components:{Table},
    methods:{
      add(){
        this.index++;
        this.arr.push({index:this.index,name:this.name,age:this.age,shan:this.shan});
       
      },
      zhi(){
        this.name=""
        this.age=""
      }
    }
}
</script>

<style scoped>
  .homebox{
    width: 100%;
    height: 100%;
  }
  .tian{
    width: 50px;
    height: 35px;
    margin-top: 15px;
    background: blue;
    color: white;
    border-radius: 10px;
    border: 0px;
    outline: none;
  }
  .chong{
    width: 50px;
    height: 35px;
    margin-top: 15px;
    background: red;
    color: white;
    border-radius: 10px;
    border: 0px;
    outline: none;

  }
  .xia{
    margin-top: 20px;
    border-top: 1px solid #ccc;
  }

</style>