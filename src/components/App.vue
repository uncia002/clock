<template>
  <div id="app">
    <div class="main-block">
      <Date/>
    </div>
    <div class="main-block">

    </div>
  </div>
</template>

<script>
import Clock from './Clock.vue'
import Date from './Date.vue'
export default {
  name: 'App',
  components: {
    Clock,
    Date,
  }
}
</script>

<style>
@font-face {
  font-family:'ta';
  src: url("../assets/Modernist.otf");
}
@font-face {
  font-family:'dual';
  src: url("../assets/dual.ttf");
}
@font-face {
  font-family:'Lato';
  src: url("../assets/Lato-Light.ttf");
}
html{
  height: 100%;
  margin:0;
}
body{
  margin: 0;
  height: 100%;
  background-color:#EEEEEE;
  overflow-y: hidden;

}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: black;
  width: 100%;
  height: 100%;
  font-size: 400px;
  display: flex;
}
.main-block{
  width: 50%;
  height: 100%;
}
</style>
