<template>
  <div class="Anime" ref="Anime">

  </div>
</template>

<script>
import anime from 'animejs';
export default {
  data() {
    return {
      frameX:0,
      frameY:0,
    }
  },
  mounted(){
    let svg = document.createElementNS("http://www.w3.org/2000/svg", "svg:svg")
    this.frameX=this.$refs.Anime.clientWidth
    this.frameY=this.$refs.Anime.clientHeight
    svg.setAttribute('width',this.frameX)
    svg.setAttribute('height',this.frameY)
    svg.setAttribute('id','svg')
    this.$refs.Anime.appendChild(svg)
    var lineDrawing = anime({
      targets: '#warai',
      strokeDashoffset: [anime.setDashoffset, 0],
      easing: 'easeInOutExpo',
      duration: 1000,
      delay: function(el, i) { return i * 150 },
    });
    this.circle()
  },
  computed:{
  },
  methods: {
    circle(){
      this.createCircle()
    },
    createCircle(){
      let x=this.frameX/2+50
      let y=this.frameY/2-300
      let x1=this.frameX/2+325
      let y1=y
      let r=300
      let x2=x1
      let y2=this.frameY/2+300
      let x3=x
      let y3=y2

      let path = document.createElementNS('http://www.w3.org/2000/svg','path');
      path.setAttribute('stroke','black')
      path.setAttribute('fill','transparent')
      path.setAttribute('stroke-width','1px')
      path.setAttribute('id','Cir')
      let root="M "+x+" "+y+" L "+x1+" "+y1+" A "+r+" "+r+" "+0+" "+1+" "+1+" "+x2+" "+y2+" L "+x3+" "+y3
      path.setAttribute('d',root)
      document.getElementById('svg').appendChild(path)
    }
  }
}
</script>

<style scoped>

.Anime{
  font-family: ta;
  position: fixed;
  height: 100%;
  width: 100%;
  transform: translateX(-50%);
  top:0;
  left: 50%;
}


</style>
