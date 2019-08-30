<template>
    <div id="collapse">
        <section class="list-content" v-if="flag">
            <el-collapse v-model="activeNameA" accordion>
                <el-collapse-item :title="a.title" :name="(index+1).toString()" v-for="(a, index) in dataArray" :key="index">
                    <div v-html="a.content" class="content-p"></div>
                </el-collapse-item>
            </el-collapse>
        </section>
        <section class="tab-content" v-if="!flag">
            <el-tabs v-model="activeNameT" type="card" @tab-click="handleClick">
                <el-tab-pane :label="a.title" :name="(index+1).toString()"  v-for="(a, index) in dataArray" :key="index"> 
                    <div v-html="a.content" class="content-p"></div>
                </el-tab-pane>
            </el-tabs>  
        </section>
    </div>
</template>

<script>
export default {
    name: 'carousel',
    data:() =>({
        activeNameA: '1',
        activeNameT: '1',
        dataArray: [],
        flag: true
    }),
    mounted(){
        let userAgentInfo = navigator.userAgent;
        let Agents = ["Android", "iPhone", "SymbianOS", "Windows Phone", "iPod", "iPad"];
        for (var i = 0; i < Agents.length; i++) {
        if (userAgentInfo.indexOf(Agents[i]) > 0) {
                this.flag = false;
                break;
            }
        }
        this.$axios.get('../../static/data.json').then(res => {
            console.log(res.data)
            this.dataArray = res.data
            console.log(this.dataArray)
        }).catch(err =>{
            console.log(err)
        })
    }
}
</script>

<style lang="scss" scoped>
#collapse{
    display: flex;
    justify-content: center;
    margin-bottom: 4rem;

    .list-content{
        width: 80%;
        .content-p{
            text-align: left;
            text-indent: 2rem;
            text-align: justify;
        }
    }
    .tab-content{
        display: flex;
        justify-content: center;
        align-items: center;
        .content-p{
            width: 80%;
            text-align: left;
            text-indent: 2rem;
            text-align: justify;
            margin: 0 2rem;
        }
    }
    
}
</style>