<template>
    <div class="salesmanship">
        <div class="salesmanship-box">
            <template v-for="(item) in databox" :key="item.id">
                <div class="Pitchsmallpictures">


                    <div class="left-1">
                        <img :src="item.imgUrl" alt="" style="width: 70%;height: 80%;">
                    </div>
                    <div class="rigth-2">
                        <div class="right-button">
                            {{ item.title }}
                        </div>
                        <div class="right-text">
                            <p>{{ item.text1 }} </p>
                            <p>{{ text2 }}</p>
                        </div>
                        <p>{{ item.text3 }}</p>
                        <p>{{ item.text4 }}</p>
                        <p>{{ item.text5 }}</p>

                    </div>

                </div>
            </template>
        </div>
    </div>
</template>
<script>

export default {
    name: 'HelloWorld',
    data() {
        return {
            databox: [
                {
                    id: 1,
                    imgUrl: 'https://tse2-mm.cn.bing.net/th/id/OIP-C.cGjCuP5ghtV5SuGhFWIqUAHaHa?w=176&h=180&c=7&r=0&o=5&pid=1.7',
                    title: '帮取送',
                    text1: '文件资料重要物品',
                    text2: '安心托付急速送全城',
                    text3: '手机数码 实时追踪安全保障',
                    text4: '紧急文件 全称安心急速护送',
                    text5: '商品配送 定制方案高效省心'
                },
                {
                    id: 2,
                    imgUrl: 'https://tse2-mm.cn.bing.net/th/id/OIP-C.cGjCuP5ghtV5SuGhFWIqUAHaHa?w=176&h=180&c=7&r=0&o=5&pid=1.7',
                    title: '帮取送',
                    text1: '文件资料重要物品',
                    text2: '安心托付急速送全城',
                    text3: '手机数码 实时追踪安全保障',
                    text4: '紧急文件 全称安心急速护送',
                    text5: '商品配送 定制方案高效省心'
                },
                {
                    id: 3,
                    imgUrl: 'https://tse2-mm.cn.bing.net/th/id/OIP-C.cGjCuP5ghtV5SuGhFWIqUAHaHa?w=176&h=180&c=7&r=0&o=5&pid=1.7',
                    title: '帮取送',
                    text1: '文件资料重要物品',
                    text2: '安心托付急速送全城',
                    text3: '手机数码 实时追踪安全保障',
                    text4: '紧急文件 全称安心急速护送',
                    text5: '商品配送 定制方案高效省心'
                },
                {
                    id: 4,
                    imgUrl: 'https://tse2-mm.cn.bing.net/th/id/OIP-C.cGjCuP5ghtV5SuGhFWIqUAHaHa?w=176&h=180&c=7&r=0&o=5&pid=1.7',
                    title: '帮取送',
                    text1: '文件资料重要物品',
                    text2: '安心托付急速送全城',
                    text3: '手机数码 实时追踪安全保障',
                    text4: '紧急文件 全称安心急速护送',
                    text5: '商品配送 定制方案高效省心'
                },
            ]
        }
    },
    methods: {

    },

}
</script>
<style scoped lang="scss">
.salesmanship {
    width: 100%;
    height: 1000px;
    background: url(../assets/image/three.png) no-repeat;
    background-size: 100% 100%;
    position: relative;

    .salesmanship-box {
        position: absolute;
        top: -110px;
        left: 50%;
        transform: translateX(-50%);
        width: 70%;
        height: 1000px;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;

        .Pitchsmallpictures {
            width: 49%;
            height: 47%;
            background-color: white;
            display: flex;

            .left-1 {
                width: 50%;
                height: 100%;
                background-color: #e7e7e7;
                overflow: hidden;
                display: flex;
                align-items: flex-end;
                justify-content: center;

            }

            .left-1 img {
                transition: transform 0.5s;
                transform: scale(1);
                /* 默认值为1 */
            }

            .left-1:hover img {
                transform: scale(1.1);
            }

            .left-1:mouseout img {
                transform: scale(1);
            }

            .rigth-2 {
                width: 50%;
                height: 100%;
                color: black;

                .right-button {
                    background-color: black;
                    width: 100px;
                    height: 50px;
                    line-height: 50px;
                    border: none;
                    color: white;
                    font-size: 18px;
                    text-align: center;
                    font-weight: 700;
                }

                .right-text {
                    margin: 50px 0;
                    margin-left: 50px;
                    font-size: 20px;
                    font-weight: 700;
                }

                .right-text>p:nth-child(1) {
                    margin-bottom: 5px;
                }

            }

            .rigth-2>p {
                margin-left: 50px;
                color: #474740;
                padding: 20px 0;
            }
        }
    }
}
</style>