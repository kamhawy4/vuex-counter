<template>
  <div>
  	<button  @click="increase" >increase</button>
  	<button  @click="decrease" >decrease</button>
  	<button  @click="increase_after_1_sec" >increase_after_1_sec</button>
   <h1>  Counter : {{counters}} </h1>
  </div>
</template>

<script>
	import {mapGetters,mapMutations} from "vuex"; 
export default {
   computed:{
        ... mapGetters(["counters"])
   },
    methods: {
        ... mapMutations(["increase", "decrease"]),
        increase_after_1_sec(){
            this.$store.dispatch('increaseAfter1Second');
        }
    }
}
</script>

