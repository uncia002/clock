<template>
  <div class="Clock">
    <div class="date">
      <h1>{{ month }}, {{day}}</h1>
    </div>
    <div class="Time">
      <h1>{{ hours }}</h1>
      <h1>:</h1>
      <h1>{{ minutes }}</h1>
      <h1>:</h1>
      <h1>{{ seconds }}</h1>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      hours:0,
      minutes:0,
      seconds:0,
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
    updateTime(){
      let now = new Date()
      this.hours=now.getHours()
      this.minutes=this.zeroPadding(now.getMinutes(), 2)
      this.seconds=this.zeroPadding(now.getSeconds(), 2)
    },
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

.Clock{
  font-family: ta;
  position: fixed;
  left:50%;
  top: 50%;
  transform: translateY(-50%) translateX(-50%);
}
.date{
  position: absolute;
  top: -50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.Time{
  display:flex;
  justify-content: center;
  font-size:200%;
  background-color: #EEEEEE;
  width:800px;
  height: 300px;
}
.Time h1{
  margin:0;
}
</style>
