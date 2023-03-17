<template>

    <div :class="Msg.from+'__Mainwrap'">
      <div :class="Msg.from+'__wrap'"  class="msg__wrap">
        <img :src="Msg.imgUrl" v-show="Msg.imgUrl ? true : false " class="msg__img" alt="">
        <p :class="Msg.from + '__txt'">{{ Msg.txt }}</p>
      </div>
        <span :class="Msg.from + '__span'" > {{ Msg.date }}</span>
    </div>
  
</template>

<script>
export default {
  name: "msgItem",
  props: {
    Msg: {
      typeof: Object,
      default: {
        txt: "",
        date: "",
        id: "",
        from: "",
        imgUrl:"",
      }
    }
  },
 data(){
   return{
     false:false,
     true:true
   }
 }
};
</script>

<style>
</style>
