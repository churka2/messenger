<template>
    <div class="phones">
        <headbar/>
        <display :messages= this.messages />
        <bottom 
        :currentId="currentId"
        @addMsg="addMsg"
        @sendImg="sendImg"
        @openModal="openModal"
         />
         <modal :currentId="currentId" v-show="modalStatus" @addMsg="addMsg" @closeModal="closeModal" :from="from" /> 
    </div>
</template>

<script>
import headbar from "@/components/headbar.vue";
import display from "@/components/displays.vue";
import bottom from "@/components/bottom.vue";
import modal from "@/components/modal.vue";

export default {
  name: "messenger",
  components: {
    headbar,
    display,
    bottom,
    modal
  },
  data() {
    return {
      messages: [],
      currentId: 1,
      modalStatus: false,
      from:''
    };
  },
  methods: {
    sendImg(Fr) {
       this.from = Fr 
       console.log(this.from);
       
    },
    addMsg(item) {
      if (item.txt != "" || item.txt2 != "") {
        this.messages.push(item);
      }
    },
    closeModal() {
      this.modalStatus = false;
    },
    openModal() {
      this.modalStatus = true;
    }
  },

};
</script>

<style>
</style>

