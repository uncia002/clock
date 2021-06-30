<template>
  <div class="layout">
    <div class="border">
    </div>
    <div class="app-detail">
      <p>Modernism is </p>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
    }
  },
  mounted(){
  },
  computed:{
  },
  methods: {
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
.border{
  position: absolute;
  border:1px solid black;
  transform: translate(-50%,-50%);
  left: 50%;
  top: 50%;
  width:calc(100% - 100px);
  height: calc(100% - 100px);
}

.appname{
  position:absolute;
  bottom:0;
  font-size:80px;
  margin:0;
}

.app-detail{
  position: absolute;
  bottom:50px;
  left:50px;
}
p{
  margin:0;
}
</style>
