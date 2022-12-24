<script setup>
import Docu from "./components/docu.vue"
import {ref,reactive} from "vue"
const current = ref(0)
const aims = reactive({
  name:"爱梅斯",
  img:"/images/aims.png",
  rate:1,
  hot:298737
})
const peco = reactive({
  name:"佩克",
  img:"/images/peco.png",
  rate:2,
  hot:198737
})
const jp = reactive({
  name:"japan",
  img:"/images/japan.png",
  rate:1,
  hot:282737
})
const ch = reactive({
  name:"china",
  img:"/images/china.png",
  rate:2,
  hot:1434322
})
const uk = reactive({
  name:"uk",
  img:"/images/uk.png",
  rate:3,
  hot:228737
})
const cat = reactive({
  name:"凯露",
  img:"/images/cat.png",
  rate:3,
  hot:28737
})
 
 
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
      <div v-show="current === 0"><Docu :item="aims"></Docu></div>
      <div v-show="current === 0"><Docu :item="peco"></Docu></div>
      <div v-show="current === 0"><Docu :item="cat"></Docu></div>
      <div v-show="current === 1"><Docu :item="jp"></Docu></div>
      <div v-show="current === 1"><Docu :item="ch"></Docu></div>
      <div v-show="current === 1"><Docu :item="uk"></Docu></div>
    </div>
  </div>
</template>
<style scoped>
.tab-wrapper{
  box-sizing: border-box;
  width: 800px;
  padding: 20px;
  background-color: rgb(45, 83, 211);
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