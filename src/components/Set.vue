<template>
  <div class="Set">
    <div class="color-select">
      <div class="color">

      </div>
      <div class="color">

      </div>
      <div class="color">

      </div>
      <div class="color">

      </div>
    </div>
    <div class="alarm">

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

.Set{
  font-family: ta;
  position: fixed;
  height: 100px;
  background-color:#111;
  bottom: 0;
  transform: translateX(-50%);
  color: #EEEEEE;
  padding:0 50px;
  left: 50%;
  border-radius: 20px 20px 0 0;
}
.color-select{
  display: flex;
}

.color{
  width: 18px;
  height: 18px;
  border-radius: 50%;
  background-color: #666666;
  margin:40px 20px;
}

.alarm{
  width: 900px;
  height: 100%;
  margin-left: 30px;
}

</style>
