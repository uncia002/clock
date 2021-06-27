<template>
  <div class="date">
    <div class="month">
      <h1>{{ month }}</h1>
      <h1> </h1>
      <h1>{{ day }}</h1>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      month:"",
      day:0
    }
  },
  mounted(){
　　let timerID = setInterval(this.updateTime, 1000);
    this.getdate()
  },
  computed:{
  },
  methods: {
    getdate(){
      let monthstr = ['January','February','March','April','May','June','July','August','September','October','November','December']
      let now = new Date()
      this.month = monthstr[now.getMonth()];
      this.day = now.getDate();
    },
    zeroPadding: function(num, len) {
  　   let zero = '';
     //0の文字列を作成
      for(var i = 0; i < len; i++) {
        zero += '0';
      }
      // zeroの文字列と、数字を結合し、後ろ２文字を返す
      return (zero + num).slice(-len);
    }
  }
}
</script>

<style scoped>
.date{
  font-family: ta;
  width:40%;
  height: 30%;
  border: 1px solid black;
  font-size: 40px;
}
.month{
  width: 500%;
  display: flex;
}
.month h1{
  margin:0;
}


</style>
