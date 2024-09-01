<template>
 
</template>

<script>


export default {
  name: 'HelloWorld',
  data() {
    return {
      isShow: false,
      UIset: false
    }
  },
  methods: {
    handleMouseOver() {
      this.isShow = !this.isShow
    },
    handleMouseOut() {
      this.isShow = !this.isShow
    },
    handleMouseOverUIset() {
      this.UIset = !this.UIset
    },
    handleMouseOutUIset() {
      this.UIset = !this.UIset

    }
  },
}
</script>

<style scoped lang="scss">
.hello {
  width: 100%;
  height: 100%
}



.cntent {
  margin-top: 100px;
  width: 100vw;
  height: 100px;
  background: gold;
}
</style>
