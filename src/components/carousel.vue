<template>
    <div id="carousel">
        <el-carousel class="content" height="650px" v-if="flag">
            <el-carousel-item v-for="item in 4" :key="item" class="items" >
                <h3 class="small">{{ title }}</h3>
                <p>{{ content }}</p>
            </el-carousel-item>
        </el-carousel>
        <el-carousel class="content-xs" :height="this.width" v-if="!flag">
            <el-carousel-item v-for="item in 4" :key="item" class="items-sx" >
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
        title: 'Hello Developer!',
        content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
        flag: true,
        width: ''
    }),
    mounted() {
        this.width = document.body.clientWidth + 'px';
        let userAgentInfo = navigator.userAgent;
        let Agents = ["Android", "iPhone", "SymbianOS", "Windows Phone", "iPod", "iPad"];
        for (var i = 0; i < Agents.length; i++) {
        if (userAgentInfo.indexOf(Agents[i]) > 0) {
                this.flag = false;
                break;
            }
        }
    },
}
</script>

<style lang="scss" scoped>
@mixin fonts($fs: 64px){
    color: #ffffff;
    font-size: $fs;
    font-weight: border;
}
.items{
    h3 {
        @include fonts;
        line-height: 100px;
        margin: 0;
        align-items: center;
        margin-top: 10%;
    }
    p {
        @include fonts(48px);
    }
}  

.items-sx{
    h3 {
        @include fonts(58px);
        line-height: 75px;
        margin: 0;
        align-items: center;
        margin-top: 20%;
    }
    p {
        @include fonts(20px);
        word-wrap:break-word;
        margin: 0 1.7rem;
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