<script setup>
import { computed } from 'vue';
const props = defineProps(["src","rate"])

const color = computed(() => {
    if(props.rate == 1)
    {return "rgb(254,45,70)"}
    else if(props.rate == 2)
    {return "rgb(245,102,1)"}
    else{
        return "rgb(247,169,1)"
    }
})
</script>
<template>
    <div>
        <div class="p-wrapper">
                    <!-- 数字 -->
                    <div class="num">{{ props.rate }}</div>
                    <!-- 照片 -->
                    <!-- //srv前面注意加上:因为绑定的是动态数据 -->
                    <div class="photo"><img :src="props.src"></div>
                </div>
    </div>
</template>
<style scoped>
.p-wrapper{
    position: relative;
}
.photo{
    width: 140px;
    height: 79px;
    border-radius: 18px;
    overflow: hidden;
}
.p-wrapper .num{
    position: absolute;
    background-color:white;
    border-bottom-right-radius: 18px;
    border-top-left-radius: 18px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 40px;
    height: 30px;
    font-weight: bold;
    background-color:v-bind(color) ;
}
.photo img {
    width: 100%;
    height: 100%;

}
</style>