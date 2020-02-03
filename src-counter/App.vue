<template>
  <div>
    <!--<p>click {{$store.state.count}} times, count is {{evenOrOdd}}</p>-->
    <p>click {{count}} times, count is {{evenOrOdd}}</p>
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
    <button @click="incrementIfOdd">increment if odd</button>
    <button @click="incrementIfAsync">increment async</button>
  </div>
</template>

<script>

  import {mapState,mapGetters,mapActions} from 'vuex'
  export default {
    computed:{
      /*evenOrOdd(){
        return this.$store.getters.evenOrOdd
      }*/
      //计算属性
      //优化代码
      ...mapState(['count']),
      ...mapGetters(['evenOrOdd'])
    },
    methods:{
      ...mapActions(['increment','decrement','incrementIfOdd','incrementIfAsync'])
      /*increment(){
        //let count = this.count
        /!*this.count = ++count*!/
        //通知vuex去增加
        this.$store.dispatch('increment') //触发store中对应的action调用
      },
      decrement(){
        /!*let count = this.count
        this.count = --count*!/
        this.$store.dispatch('decrement') //触发store中对应的action调用
      },
      incrementIfOdd(){
        /!*let count = this.count
        if(count%2===1){
          this.count = count+1
        }*!/
        this.$store.dispatch('incrementIfOdd') //触发store中对应的action调用
      },
      incrementIfAsync(){
        /!*setTimeout(()=>{
          let count = this.count
          this.count = count+1
        },1000)*!/
        this.$store.dispatch('incrementIfAsync') //触发store中对应的action调用
      }*/
    }
  }
</script>

<style>

</style>
