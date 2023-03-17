<template>

<div class="container messenger__wrap">
     
        <div class="phone-one__display phone__display">
          <Msg
          v-for="(Msg, index) in messages" 
          :key="index"
          :Msg="Msg"
        />
        </div>
        
        <div class="phone-two__display phone__display">
        <Msg
          v-for="(Msg, index) in messages" 
          :key="index"
          :Msg="Msg"
        />
        </div>
</div>
</template>

<script>
import Msg from "@/components/msgItem.vue"
export default {
  name: "PhoneDisplays",
   components:{
    Msg,
  },
  props:{
    messages:{
        typeof:Array,
    },
  },
  data() {
    return{
            
    }
  },
  
  
};
</script>

<style>

</style>
