<template>
    <div id="lists">
        <el-row width="100%" class="items_list">
            <el-col :xs="20" :sm="20" v-for="(o, index) in 3" :key="index" class="item">
                <el-card>
                    <img src="http://via.placeholder.com/400x300" class="image">
                    <section class="content">
                        <span>{{ content[index] }}</span>
                    </section>
                    <footer class="bottom clearfix">
                        <el-button type="text" class="button" round>READ MORE</el-button>
                    </footer>
                </el-card>
            </el-col>
        </el-row>
    </div>
</template>

<script>
export default {
    name: 'lists',
    data:() =>({
        content:[
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco.'
        ]
    }),
}
</script>

<style lang="scss" scoped>
#lists{
    margin: 3rem 0;
    .item{
        width: 325px;
        height: 495px;
        display: flex;
        justify-items: center;
        align-items: center;
        margin-left: 35.80px;
        .image{
            // margin-top: 1rem;
            margin-bottom: 21px;
            width: 283.69px;
            height: 212.56px;
            border-radius: 3%;
        }
        .content{
            height: 154px;
        }
        .button{
            border: 1px solid #000;
            color: #000;
            margin-top: 1rem;
        }
    }
}
@media only screen and (min-width: 736px)  {
    .items_list{
        display: flex;
        justify-content: center;
    }
}

</style>