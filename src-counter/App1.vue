<template>
  <div>
    <p>click {{count}} times, count is {{evenOrOdd}}</p>
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
    <button @click="incrementIfOdd">increment if odd</button>
    <button @click="incrementIfAsync">increment async</button>
  </div>
</template>

<script>

  export default {
    data(){
      return {
        count:0
      }
    },
    computed:{
      evenOrOdd(){
        return this.count%2===0?'偶数':'奇数'
      }
    },
    methods:{
      increment(){
        let count = this.count
        this.count = ++count
      },
      decrement(){
        let count = this.count
        this.count = --count
      },
      incrementIfOdd(){
        let count = this.count
        if(count%2===1){
          this.count = count+1
        }
      },
      incrementIfAsync(){
        setTimeout(()=>{
          let count = this.count
          this.count = count+1
        },1000)
      }
    }
  }
</script>

<style>

</style>
