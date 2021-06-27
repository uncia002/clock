<template>
  <div id="app">
    <Date/>
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
html{
  height: 100%;
  margin:0;
}
body{
  margin: 0;
  height: 100%;
  background-color:#EEEEEE;
  overflow-y: hidden;
  user-select: none;

}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: black;
  width: 100%;
  height: 100%;
  font-size: 400px;
}
</style>
