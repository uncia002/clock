<template>
  <div class="date">
    <div style="border-bottom:solid 1px black;" class="month">
      <h1 style="margin-right:50px;">{{ month }}</h1>
      <h1>{{ day }}</h1>
    </div>
    <div class="time">
      <div class="time-char">
        <div class="">
          <h1>{{ hours }}</h1>
        </div>
        <h1>:</h1>
        <div class="">
          <h1>{{ minutes }}</h1>
        </div>
        <h1>:</h1>
        <div class="">
          <h1>{{ seconds }}</h1>
        </div>
      </div>
      <div class="where">
        <a>in japan</a>
      </div>
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
      // let monthstr = ['睦月','如月','弥生','卯月','皐月','水無月','文月','葉月','長月','神無月','霜月','師走']
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
  width:100%;
  height: 35%;
  border: 1px solid black;
  font-size: 90px;
}
.month{
  padding-left: 30px;
  display: flex;
}
.month h1{
  margin:0;
}
.time{
  display: flex;
  height: 100px;
  padding-left: 30px;
}

.time-char{
  display: flex;
}
.time-char div{
  width: 130px;
}

.time-char h1{
  font-size: 90px;
  margin:0;
  text-align: center;
}
.where{
  height: 100%;
  font-size: 2rem;
  font-family: 'Lato';
  position: relative;

}
.where a{
  position:absolute;
  bottom:0;
}
.kanji{
}


</style>
