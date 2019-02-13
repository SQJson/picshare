<template>
    <div class="mine">
       <div class="mine-top">
           <div class ="mine-avatar">
               <image class="mine-avatar-img" src="../../static/images/mine/avatar.jpg"></image>
               <br/><br/>
               <h4>哎呦喂</h4>
           </div>
           <image src="https://image.weilanwl.com/gif/wave.gif" mode='scaleToFill' class='gif-wave'></image>
       </div>
       <div class="mine-para shadow-warp">
           <div class="mine-para-box">
           <div class="mywork">
               <p><strong>{{myworkCount}}</strong></p>
               <span>作品</span>
            </div>
           <div class="like">
               <p><strong>{{likcTotal}}</strong></p>
               <span>点赞</span>
            </div>
           <div class="view">
               <p><strong>{{viewCount}}</strong></p>
               <span>查看</span>
            </div>
           </div>
       </div>
       <div class="mine-panel">
           <div class="panel-item">
               我的作品
           </div>
           <div class="panel-item">
               投诉建议
           </div>
           <div class="panel-item">
             ……
           </div>
           <div class="panel-item">
             ……
           </div>
       </div>
    </div>
</template>

<script>
export default {
  data () {
    return {
      myworkCount:0,
      likcTotal:0,
      viewCount:0
    }
  },
  components: {
    
  },
  methods: {
    loadPage(){
        let that = this;
        wx.showLoading({
        title: '数据加载中',
        mask: true,
      })
      let i = 0;
      console.log("i am in ")
      numDH();
      function numDH() {
        if (i < 20) {
            setTimeout(function() {
              that.myworkCount= i,
              that.likcTotal= i,
              that.viewCount= i
            i++
            numDH();
          }, 20)
        } else {
            that.myworkCount=that.coutNum(999),
            that.likcTotal=that.coutNum(8888),
            that.viewCount= that.coutNum(77777)
        }
      }
      wx.hideLoading()
    },
    coutNum(e) {
      if (e > 1000 && e < 10000) {
        e = (e / 1000).toFixed(1) + 'k'
      }
      if (e > 10000) {
        e = (e / 10000).toFixed(1) + 'W'
      }
      return e
    },
  },
  created () {
      this.loadPage()
  }
}
</script>

<style scoped>
.mine{
    background-color: #eeeeee;
    position: absolute;
    height: 100%;
    width: 100%
}
.mine-top{
    background-image: url("https://image.weilanwl.com/color2.0/index.jpg");
    height: 400rpx;
    background-repeat: no-repeat;
    background-size: 100% 100%;
}
.gif-wave{
  position: absolute;
  width: 100%;
  left: 0;
  top: 300rpx;
  z-index: 99;
  mix-blend-mode: screen;  
  height: 100rpx;   
}
.mine-avatar{
    position: relative;
    height: 170rpx;
    width: 170rpx;
    margin: 0 auto;
    top: 35px;
    text-align: center;
    font-family: 'arial'
}
.mine-avatar-img{
    position:relative;
    height: 100%;
    width: 100%;
    border-radius: 50%;
}
.mine-para{
    position:absolute;
    width: 100%;
    height: 150rpx;
}
.mine-para-box{
    position: absolute;
    height: 150rpx;
    width: 100%;
    background-color:white;
     display: flex;
    flex-direction: row;
    justify-content:center;
}
.mine-para-box div{
    height: 110rpx;
    width: 250rpx;
    margin: 20rpx 0;
    text-align: center;
    padding-top: 5rpx;
    font-size: 45rpx;
}
.like{
    border-left: 1rpx solid rgba(175, 175, 175, 0.3);
    border-right: 1rpx solid rgba(175, 175, 175, 0.3);
    color: rgb(19, 170, 5)
}
.mywork{
    color: orange;
}
.view{
    color: rgb(25, 130, 250)
}
.mine-para div span{
    color: gray;
    font-size: 25rpx;
    font-family: 'arial'
}
.shadow-warp {
  position: relative;
  box-shadow: 0 0 10rpx rgba(0, 0, 0, 0.1);
}

.shadow-warp:before, .shadow-warp:after {
  position: absolute;
  content: "";
  top: 20rpx;
  bottom: 30rpx;
  left: 20rpx;
  width: 50%;
  box-shadow: 0 30rpx 20rpx rgba(0, 0, 0, 0.2);
  transform: rotate(-3deg);
  z-index: -1;
}

.shadow-warp:after {
  right: 20rpx;
  left: auto;
  transform: rotate(3deg);
}
.mine-panel{
    position: relative;
    height: 400rpx;
    width: 600rpx;
    /* background-color: red; */
    margin: 0 auto;
    top: 50rpx;
    border-radius: 30rpx;
    background-color: white;
    
}
.panel-item{
    position: relative;
    height: 80rpx;
    width: 95%;
    margin: 0 auto;
    border-bottom: 1rpx solid rgba(175, 175, 175, 0.3);
    line-height: 80rpx;
    font-size: 30rpx;
}
</style>
