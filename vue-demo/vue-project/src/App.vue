<script setup>
import Docu from "./components/docu.vue"
import {ref,reactive} from "vue"
const current = ref(0)
// 角色
const chas = reactive([
  {
    name:"爱梅斯",
  img:"/images/aims.png",
  rate:1,
  hot:298737
},
  {
  name:"佩克",
  img:"/images/peco.png",
  rate:2,
  hot:198737
},
{
  name:"凯露",
  img:"/images/cat.png",
  rate:3,
  hot:28737
}])
// 工会
const teams = reactive([{
  name:"china",
  img:"/images/china.png",
  rate:1,
  hot:1434322
},
{
  name:"uk",
  img:"/images/uk.png",
  rate:2,
  hot:228737
},
{
  name:"japan",
  img:"/images/japan.png",
  rate:3,
  hot:182737
}])
const ChamaxHot = chas[0].hot
const teamMaxHot = teams[0].hot
</script>
<template>
  <!-- 外部容器 -->
  <div class="tab-wrapper">
    <!-- 头部 -->
    <header class="tab-head">
      <!-- 两个按钮 -->
      <div @click="current = 0" class="tab-button" :class="{active: current === 0}">热门角色</div>
      <div @click="current = 1" class="tab-button" :class="{active: current === 1}">热门工会</div>
    </header>
    <!-- 主体 -->
    <div class="main">
      <!-- <div v-show="current === 0"><Docu :item="cha" :team="team"></Docu></div> -->
      <div v-show="current === 0">
        <Docu 
        v-for="cha in chas"
        :item="cha"
        :maxHot="ChamaxHot"
        ></Docu>
      </div>
      <div v-show="current === 1">
        <Docu 
        v-for="team in teams"
        :item="team"
        :maxHot="teamMaxHot"
        ></Docu>
      </div>
    </div>
  </div>
</template>
<style scoped>
.tab-wrapper{
  box-sizing: border-box;
  width: 800px;
  padding: 20px;
  background-color: rgb(45, 83, 211);
  margin:0 auto;
  border-radius: 20px;
}
.tab-head{
  display: flex;
  border-radius: 10px;
  overflow: hidden;
}
.tab-button{
  background-color: white;
  font-size: 30px;
  flex: auto;
  padding: 10px 0;
  text-align: center;
  cursor: pointer;
  transition: 1s;}
.tab-button:not(.active):hover{
  color: red;
}
.active{
  background-color: red;
  color: white;
}
</style>