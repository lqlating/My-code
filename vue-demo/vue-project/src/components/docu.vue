<script setup>
import photo from './photo.vue'
import hot from './hot.vue'
const props = defineProps(["item","team","maxHot"])

</script>
<template>
    <div>
        <!-- 单个成员容器 -->
        <div class="wrapper">
            <!-- 头像容器 -->
            <div class="head">
               <photo :rate="props.item.rate" :src="props.item.img"></photo>
                <!-- 热度容器 -->
            <hot :name="props.item.name" :hot="props.item.hot" :maxHot="maxHot"></hot>
            </div>

        </div>
    </div>
</template>
<style scoped>
.wrapper {
    padding: 10px;
}

.head {
    display: flex;
}
</style>