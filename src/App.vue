<template>
    <div id="app">
        <div class='top' @click='showPopup("top")'>从屏幕上方上滑入</div>
        <div class='bottom' @click='showPopup("bottom")'>从屏幕下方上滑入</div>
        <Popup ref='top' from='top' @hideFun='hideFun' @showFun='showFun' @cancelFun='cancelFun' @confirmFun='confirmFun' :action-show='true'>
            <div class="test" >
                我是从屏幕上方滑入的
            </div>
        </Popup>
        <Popup ref='bottom'>
            <div class="test">
                我是从屏幕下方滑入的
            </div>
        </Popup>
    </div>
</template>
<script>
import Popup from './components/Popup'

export default {
  name: 'app',
  components: {
      Popup
  },
  methods:{
      showPopup(el){
          this.$refs[el].show = true;
      },
      hideFun(){
        console.log('hide popup');
      },
      showFun(){
          console.log('show popup');
      },
      cancelFun(){
        console.log('cancle popup');
      },
      confirmFun(){
          console.log('confirm popup');
      }
  }
}
</script>

<style lang='less' scoped>
    #app {
        width: 100%;
        height: 100%;
        box-sizing: border-box;
        padding: .12rem;
        .top,
        .bottom{
            display: block;
            width: 100%;
            height: .44rem;
            border-radius: .06rem;
            margin-bottom: .1rem;
            background-color: #20a0ff;
            color: #fff;
            font-size: .16rem;
            text-align: center;
            line-height: .44rem;

        }
    }
    .test{
        width: 100%;
        height: 2rem;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: .14rem;
        color: #666;
    }
</style>
