<template>
  <div id="app">
    <videoPlayer class="vjs-custom-skin videoPlayer" :options="playerOptions" width="70%"></videoPlayer>
  </div>
</template>
<script>
import { videoPlayer } from 'vue-video-player'

export default {
  name: 'video',
  components: { videoPlayer },
  data() {
    return {
      playerOptions: {
        height: '600', //播放器高度
        sources: [
          {
            type: 'rtmp/mp4', //视频流协议，如果是hls，需要后端开启跨域
            // 内测地址（cctv3 视频流）
            src: 'http://ivi.bupt.edu.cn/hls/cctv3hd.m3u8'
          }
        ],
        techOrder: ['flash'],
        autoplay: true, //自动播放
        controls: true //编辑器控件
        //更多参数建议查看vue-video-player官网，这里只提供参考
      }
    }
  },
  mounted() {
    console.log(this.playerOptions)
  }
}
</script>
<style>
</style>
