<template>
<div>
  <p>Reaction time - {{ score }} ms </p>
  <p class="rank"> {{ rank }} </p>
</div>
</template>

<script>
export default {
props: ['score', 'rank'],
data(){
    return{
        mounted(){
            if (this.score < 250){
                this.rank = 'Ninja Fingers'
            }else if (this.score < 400){
                this.rank = 'Rapid Reflexers'
            }else {
                this.rank = 'snail pace ....'
            }
        }
    }
}
}
</script>

<style>
.rank {
    font-size: 1.4em;
    color: #0faf87;
    font-weight: bold;
}
</style>