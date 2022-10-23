<template>
  <div class="block" v-if="showBlock" @click="stopTimer">click me</div>
</template>

<script>
export default {
    props: ['delay'],
    data(){
      return{
        showBlock: false,
        timer: null, //setInterval with 10 milliseconds
        reactionTime: 0 // add 10 milliseconds into it
      }
    },
    mounted(){
      console.log("component mounted");
      setTimeout(()=> {
        this.showBlock = true;
        this.startTimer()
        console.log(this.delay);
      }, this.delay)
      
    },
    // updated(){
    //   console.log('component updated');
      
    // },
    // unmounted(){
    //   console.log('component unmounted');
    // }
    methods: {
      startTimer(){
        this.timer = setInterval(()=> {
          this.reactionTime += 10
        },10) // 10 milliseconds
      },
      stopTimer(){
        clearInterval(this.timer)
        //console.log(this.reactionTime); 
        /**We want to emit the event for having custom events after it stops time and clears the interval*/
        this.$emit('end', this.reactionTime) //second argument will be any data we want to send it along with this event
      }
    }
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 10px;
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
