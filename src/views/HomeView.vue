<template>
  <div class="home">
    <div class="body">
      <button type="primary" @click="setQcode" style="width: 150px;"> 生成二维码 </button>
      <div class="qrcode2" ref="fantasy"></div>
    </div>
  </div>
</template>

<script>
import QRCode from 'qrcodejs2';
export default {
  name: 'Demo',
  components: { QRCode },
  data() {
    return {
    }
  },
  methods: {
    setQcode() {
      let url = 'https://www.baidu.com/' || window.location.href;
      new QRCode(this.$refs.fantasy, {
        text: url,
        width: 200,
        height: 200,
        colorDark: '#000000',
        colorLight: '#ffffff',
        correctLevel: QRCode.CorrectLevel.H
      });
    },
  },
}
</script>

<style scoped>

</style>
