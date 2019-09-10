<template>
  <div class="tablebox">
    <h2>用户信息表:</h2>
      <div class="shang">
        <li v-for="(item,index) in list" :key="index">
          {{item}}
        </li>
      </div>
        <div class="di" v-if="option.length">
           <li v-for="(item,index) in option" :key="index">
            <span>{{item.index}}</span>
            <span>{{item.name}}</span>
            <span>{{item.age}}</span>
            <span  @click="shan(index,item)">{{item.shan}}</span>
          </li>
          <button @click="btnFn">删除全部</button>
       </div>
       <span v-else>暂无数据……</span>

        <!-- <Shan :qu="qu"/> -->
        <div class="loadingbox" v-if="flag">
          <h3>确定要删除吗? <span @click="cha">X</span></h3>
          <button @click="qu">取消</button>
          <button @click="que">确认</button>
        </div>
  </div>
</template>

<script>
import Shan from "./shan"
export default {
    data(){
      return {
        list:["序号","名字","年龄","操作"],
        flag:false
      }
    },
    props:["option"],
    components:{Shan},
    methods:{
      shan(index,item){
        this.flag=true;
      },
      que(){
        this.option.splice(0,1)
        this.flag=false;
      },
      cha(){
        this.flag=false;
      },
      qu(){
        this.flag=false;
      },
      btnFn(){
        this.option.splice(0)
      }

    },
    
}
</script>

<style scoped>
  .tablebox{
    width: 90%;
    margin:0 auto
  }
  .shang{
    width: 90%;
    height: 40px;
    display: flex;
    justify-content: space-around;
    list-style: none;
    line-height: 40px;
    border-top: 1px solid #ccc;
    border-bottom: 1px solid #ccc;
  }
  .shang li{
    flex: 1;
    text-align: center;
    border-right: 1px solid #ccc;
    border-left: 1px solid #ccc;

  }
  .di{
    width: 100%;
    margin-top: 10px;
    border: 1px solid #ccc;
    height: 100px;
    list-style: none;
    /* flex-wrap: wrap; */
    overflow: auto;
  }
  .di li{
    width: 100%;
    display: flex;
    justify-content: space-around;
    line-height: 40px;
    text-align: center;
    height: 30px;
    /* border: 1px solid #ccc; */
  }
 .loadingbox{
   width: 100%;
   height: 100%;
   background: black;
   opacity: .8;
   color: white;
   position: fixed;
   transform: rotate3d(100);
   top: 0;
   left: 0;
 }

 
</style>