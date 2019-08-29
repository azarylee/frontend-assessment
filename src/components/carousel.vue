<template>
    <div id="carousel">
        <el-carousel class="content">
            <el-carousel-item v-for="item in 4" :key="item" class="items" v-if="flag">
                <h3 class="small">{{ title }}</h3>
                <p>{{ content }}</p>
            </el-carousel-item>
            <el-carousel-item v-for="item in 4" :key="item" class="items-sx" v-if="!flag">
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
        content: 'Lorem ipsum dolor sit amet,consectetur adipiscing elit.',
        flag: true,
    }),
    mounted() {
        console.log(document.body.clientWidth)
        let width = document.body.clientWidth;
        if(width < 736){
            console.log($('.content'))
            this.flag = false;
            
            // $('.content').css({"width":'600px!important',"height":'600px!important'});
            $('.el-carousel__container').height(411);
        }
    },
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
    .content{
        width: 1920px;
        height: 650px;
    }
}  
.items:nth-child(2n) {
    background: url('http://via.placeholder.com/1920x650');
}

.items:nth-child(2n+1) {
    background-color: #d3dce6;
}
.items-sx:nth-child(2n) {
    background: url('http://via.placeholder.com/600x600');
    background-size: cover;
}
.items-sx:nth-child(2n+1) {
    background-color: #d3dce6;
    background-size: cover;
}
</style>