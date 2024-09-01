<template>
    <div class="commercial">
        <div class="commercial-centent">
            <p>一呼百应， UU跑腿为您提供高效便捷的同城即时生活服务</p>
            <span>
                百万UU跑男实名认证，同城急事平均37分钟搞定
            </span>
        </div>
    </div>
</template>
<script>

export default {
    name: 'HelloWorld',
    data() {
        return {

        }
    },
    methods: {

    },

}
</script>
<style scoped lang="scss">
.commercial {
    height: 300px;
    width: 100%;
    .commercial-centent {
        width: 100%;
        height: 100%;
        text-align: center;
        margin-top: 100px;
    }
    .commercial-centent>p{
          font-size: 30px;
          color: black;
          font-weight: 700;
          margin-bottom: 5px;
    }
    .commercial-centent>span{
        
         color: #bfc1c3;
    }
}
</style>