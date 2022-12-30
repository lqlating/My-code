<script setup>
import { computed } from '@vue/reactivity';
const props = defineProps(["name","hot","maxHot"])

const width = computed(() => {
    // 计算百分比
    return (props.hot / props.maxHot) * 100 + "%"
})
</script>
<template>
  
        <div class="hot">
            <div class="name">{{ props.name }}</div>
            <div class="line">
                <div class="inner">
                    {{ props.hot }}热度
                </div>
            </div>
        </div>
 
</template>
<style scoped>

.hot{
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    flex: auto;
    margin-left: 20px;
}
.hot .name{
    color: white;
    font-weight: bold;
}
.hot .line{
    background-color: rgb(3, 37, 103);
    border-radius: 20px;
    text-indent: 0.5em;
    overflow: hidden;
}
.hot .inner {
    width: v-bind(width);
    border-radius: 20px;
    background-image: linear-gradient(
        90deg,
        rgb(187, 3, 52) 50%,
        rgb(66, 2, 12)
    );
    white-space: nowrap;
    color: aliceblue;
}
</style>