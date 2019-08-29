<template>
    <div class="block">
    <el-carousel width="1920px" height="650px">
      <el-carousel-item v-for="item in 4" :key="item" class="items">
        <h3 class="small">{{ title }}</h3>
        <p>{{ content }}</p>
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<script>
export default {
    name: 'carousel',
    data:() =>({
        title: 'Hello Developer',
        content: 'Lorem ipsum dolor sit amet,consectetur adipiscing elit.'
    }),
}
</script>

<style lang="scss" scoped>
// /* @import "../assets/css/index.scss" */
.items{
    h3 {
        color: #ffffff;
        font-size: 64px;
        line-height: 100px;
        margin: 0;
        align-items: center;
        margin-top: 10%;
    }
    p {
        color: #ffffff;
        font-size: 48px;
    }
}  
.items:nth-child(2n) {
    background: url('http://via.placeholder.com/1920x650');
}

.items:nth-child(2n+1) {
    background-color: #d3dce6;
}
</style>