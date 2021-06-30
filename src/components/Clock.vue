<template>
  <div class="clock">
    <div class="date">
      <h1>{{ month }}</h1>
      <h1>{{date}} {{day}}</h1>
    </div>
    <div class="place">
      <h1>Japan  Tokyo</h1>
    </div>
    <div class="Time">
      <div class="time-block">
        <h1>{{ hours }}</h1>
      </div>
      <h1 class="colon">:</h1>
      <div class="time-block">
        <h1>{{ minutes }}</h1>
      </div>
      <h1 class="colon">:</h1>
      <div class="time-block">
        <h1>{{ seconds }}</h1>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      hours:0,
      minutes:0,
      seconds:0,
      month:"",
      date:0,
      day:0,
      dayStr:[ "Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday" ],
      info:null,
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
      this.date = now.getDate();
      this.day = this.dayStr[now.getDay()]
    },
    zeroPadding(num, len) {
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
h1{
  margin:0;
}
.clock{
  font-family: ta;
  position: fixed;
  left:50%;
  top: 50%;
  transform: translateY(-50%) translateX(-50%);
}
.date{
  position: absolute;
  left:0;
  top:-40px;
}
.Time{
  display:flex;
  justify-content: center;
  text-align: center;
  font-size:80px;
  background-color: #EEEEEE;
}
.colon{
  width: 40px;
}
.time-block{
  width:190px;
}
.place{
  position: absolute;
  bottom:-20px;
  right: 0;
  width: 200px;
  border-radius: 30px;
  text-align: right;

}
</style>
