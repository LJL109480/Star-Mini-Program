<template>
  <div class="bg">
    <img class="logo" src="/static/image/QQ图片20190120192829.png" alt="">
    <div class="mark">最高得分：1254</div>
    <button class="start">开始游戏</button>
    <div class="record">最高纪录</div>
    <div class="lines"></div>
    <div class="toolBar">
      <button class="install" v-on:click="installClick">设置</button>
    </div>
    <div class="coverLayer" v-if="swich">
      <div class="install_detalls">
        <div class="detalls_text">
          <p class="text">设置</p>
          <p class="close" v-on:click="installClick">X</p>
        </div>
        <div class="install_sound">
          <div class="sound_border">
            <span class="sound_text">音效</span>
            <div class="sound_swith" v-on:click="soundClick">
              <span v-if="sound">P</span>
            </div>
            <span class="swith_text">{{msg}}</span>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>
<script>
  export default{
  data(){
    return{
      swich:false,
      sound:true,
      msg:"开"
    }
  },
  methods:{
    installClick(){
      this.swich = !this.swich;
    },
    soundClick(){
      if(this.sound = true){
        this.sound = false
        this.msg = "关"
      }
      if(this.sound = false){
        this.sound = true
        this.msg = "开"
      }
    }
  }
  }
</script>
<style scoped>
  .bg{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .logo{
    width: 630rpx;
    height: 300rpx;

  }
  .mark{
    width: 100%;
    text-align: center;
    margin: 30rpx 0;
    font-size: 33rpx;
    font-weight: bold;

  }
  .start{
    width: 400rpx;
    height: 100rpx;
    background: yellow;
    color: white;
    font-weight: bold;
    border-radius: 30rpx;

  }
  .record{
    font-weight: bold;
    font-size: 35rpx;
    font-family: "新宋体";
    margin-top: 20rpx;

  }
  .lines{
    width: 132rpx;
    border: 0.5rpx solid black;

  }
  .toolBar{

  }
  .install{
    margin-top: 50rpx;
    background: white;
    font-size: 30rpx;
    font-family: "微软雅黑";
  }
  .coverLayer{
    width: 100%;
    height: 800rpx;
    position: absolute;
    top:0;
    background: gainsboro;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgba(0,0,0,0.3);
  }
  .install_detalls{
    width: 600rpx;
    height: 600rpx;
    background: dodgerblue;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .detalls_text{
    width: 100%;
    height: 100rpx;
    position: relative;
  }
  .text{
    color: yellow;
    text-align: center;
    font-weight: bold;
    font-size: 40rpx;
  }
  .close{
    position: absolute;
    top:-2rpx;
    right: 30rpx;
    color: white;
    font-weight: bold;
    font-size: 50rpx;
  }
  .install_sound{
    width: 80%;
    height: 400rpx;
    background: deepskyblue;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .sound_border{
    width: 70%;
    height: 100rpx;
    display: flex;
    justify-content: space-around;
    align-items: center;
    border: 1rpx solid grey;
    color: white;
    font-weight: bold;
    font-family: Arial;
  }
  .sound_swith{
    width: 50rpx;
    height: 50rpx;
    border: 1rpx solid grey;
    text-align: center;
    line-height: 50rpx;
  }
</style>
