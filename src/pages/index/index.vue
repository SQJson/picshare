<template>
  <div class="recommond">
    <div class="add-pic">
      <image src="../../static/images/index/add.png"></image>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      
    }
  },
  components: {
    
  },
  methods: {
    
  },
  created () {
   
  }
}
</script>

<style scoped>
.recommond{
   background-color: #eeeeee;
    position: absolute;
    height: 100%;
    width: 100%
}
.add-pic{
  position: absolute;
  height: 100rpx;
  width: 100rpx;
  border-radius: 60%;
  margin: 0 auto;
  background-color: #13AA05;
  bottom: 40rpx;
  left: 50%;
  margin-left: -50rpx;
  box-shadow: 0 0 20rpx  rgb(175, 175, 175);
}
.add-pic image{
  position: relative;
  height: 100%;
  width: 100%;
}
</style>