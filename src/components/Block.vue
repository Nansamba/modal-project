<template>
<div class = "block" v-if="showBlock" @click="stopTimer" >click me</div> 
</template>

<script>


export default {
  prop: ['delay'],
  data(){
    return{
      showBlock: false,
      timer: null,
      reactionTime: 0
    }
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true
      this.startTimer()
    }, this.delay)
  },
  methods: {
    startTimer(){
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10)
    },
    stopTimer(){
      clearInterval(this.timer)
      this.$emit('end', this.reactionTime)
    }
  } 
  } 

</script>

<style>
.block {
    width: 400px;
    background: #00ffaa;
  text-align: center;
  color: white;
  margin: 40px auto;
  padding: 100px 0;
  border-radius: 10px;
}
</style>
