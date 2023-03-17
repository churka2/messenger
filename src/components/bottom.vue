<template>
<div class="container messenger__wrap">
    <div class="phone-one__bottom phone__bottom">
            <input 
            @focus="inputFocus('txtTwo')"
            type="text" 
            class="bottom__input" 
            v-model="txt" 
            v-on:keydown.enter="addMsg"
            placeholder="Написать сообщение...">
                        
            <button 
            v-if="txt == ''" 
            class="camera__btn"
            @click="sendImg('alex')">
            <img src="../assets/img/camera.svg" alt="" class="camera__img"></button>
            
            <button 
            v-else
            class="send__btn" 
            @click="addMsg">
            <img src="../assets/img/Send.svg" alt="" class="send__img"></button>
        </div>
        
        <div class="phone-two__bottom phone__bottom">
            <input 
            @focus="inputFocus('txt')"
            type="text" 
            class="bottom__input" 
            v-model="txtTwo" 
            v-on:keydown.enter="addMsg"
            placeholder="Написать сообщение...">
                        
            <button 
            v-if="txtTwo == ''" 
            class="camera__btn"
            @click="sendImg('evgen')">
            <img src="../assets/img/camera.svg" alt="" class="camera__img"></button>
            
            <button 
            v-else
            class="send__btn" 
            @click="addMsg"
            >
            <img src="../assets/img/Send.svg" alt="" class="send__img"></button>
        </div>
</div>
        
        
</template>

<script>
export default {
    name:"phoneBottoms",
    props:{
        currentId:Number
    },
data(){
    return{
        txt:'',
        txtTwo:'',
        id:this.currentId,
    }
},

methods:{
    inputFocus(input){
        if (input == "txt") {
            this.txt = ''
        }else if(input == "txtTwo"){
             this.txtTwo = ''
        }else{
            console.log(ERROR);
        }
    },
    
    addMsg(){
        
        let d = new Date(),
        H = d.getHours(),
        M = d.getMinutes(),
        D = ""
        if (M > 9) {
             D = H + ':' + M
        }else{
             D = H + ':0' + M
        }
        
        
        
        if (this.txt != "" && this.txtTwo == ""){
            
            const item = {
                txt: this.txt,
                date: D,
                id: this.id++,
                from: 'alex',
            };
            this.$emit("addMsg", item);
            this.txt = this.txtTwo = "";
            
        }else if(this.txtTwo != "" && this.txt == ""){
            
            const item = {
                txt: this.txtTwo,
                date: D,
                id: this.id++,
                from: 'evgen',
            };
            this.$emit("addMsg", item);
            this.txt = this.txtTwo = "";
        }else{
            console.log('error');
             this.txt = this.txtTwo = "";
        }
    },
    sendImg(fromWho){
       let Fr = fromWho
        this.$emit("sendImg", Fr)
        this.$emit("openModal")
    },
    
},
}
</script>

<style>

</style>
