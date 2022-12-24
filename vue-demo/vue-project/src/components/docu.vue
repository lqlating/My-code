<script setup>
const props = defineProps(["item"])
</script>
<template>
    <div>
        <!-- 单个成员容器 -->
        <div class="wrapper">
            <!-- 头像容器 -->
            <div class="head">
                <div class="p-wrapper">
                    <!-- 数字 -->
                    <div class="num">{{ props.item.rate }}</div>
                    <!-- 照片 -->
                    <!-- //srv前面注意加上:因为绑定的是动态数据 -->
                    <div class="photo"><img :src="props.item.img"></div>
                </div>
                <!-- 热度容器 -->
                <div class="hot">
                    <div class="name">{{props.item.name}}</div>
                    <div class="line">
                        {{ props.item.hot }}
                        <div class="inner">

                        </div>
                    </div>
                </div>
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
}
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
    background-color:rgba(204, 15, 15, 0.708);
    border-radius: 5px;
    color: white;
    font-weight: bold;
    padding-left: 20px;
    

}
.photo img {
    width: 100%;
    height: 100%;

}
</style>