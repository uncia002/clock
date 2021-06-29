<template>
  <div class="layout">
    <div class="">
      {{scrollY}}
    </div>
    <h1 class="appname">ism</h1>
  </div>
</template>

<script>

export default {
  data() {
    return {
      start_pos:0,
      current_pos:0,
      scrollY:0,
    }
  },
  mounted(){
    window.addEventListener('scroll', function(e){
      this.current_pos = window.scrollTop;
      if (this.current_pos > this.start_pos) {
        console.log('down');
      } else {
        console.log('up');
      }
      this.window.scrollTop
      this.start_pos = this.current_pos;
    });

  },
  computed:{
  },
  methods: {
    switchActive(Y){
      if(Y>1){}
    },
    handleScroll() {
      this.current_pos=window.scrollTop
    }
  }
}
</script>

<style scoped>

.layout{
  font-family: ta;
  position: fixed;
  width: 100%;
  height: 100%;
}

.appname{
  position:absolute;
  bottom:0;
  font-size:80px;
  margin:0;
}
</style>
