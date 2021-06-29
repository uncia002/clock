<template>
  <div id="app">
    <!-- <div class="main-block">
      <Date/>
    </div>
    <div class="main-block">

    </div> -->
    <Clock/>
    <Layout/>
    <Set/>
  </div>
</template>

<script>
import Clock from './Clock.vue'
import Date from './Date.vue'
import Layout from './Layout.vue'
import Set from './Set.vue'

export default {
  name: 'App',
  components: {
    Clock,
    Date,
    Layout,
    Set
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

}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: black;
  width: 100%;
  height: 200%;
  display: flex;
}
</style>
