<template>
    <Transition name="scale">
    <div class="modal" @click="closeModal">
      <div class="modal__content" @click.stop="">
        <h3 class="modal__h3">Отпрвить Фотографию</h3>
        <div class="modal__inputs">
          <div class="input__content">
            <span class="input__label">URL</span>
            <input
              type="text"
              class="modal__input"
              placeholder="URL"
              v-model="imgUrl"
            />
          </div>
          <div class="input__content">
            <span class="input__label">Комментарий</span>
            <input
              type="text"
              class="modal__input"
              placeholder="Комментарий"
              v-model="txt"
            />
          </div>
        </div>
        <div class="modal__btns">
          <button class="modal__btn close" @click="closeModal" >Отмена</button>
          <button class="modal__btn send"  @click="addMsg" >Отправить</button>
        </div>
      </div>
    </div>
  </Transition>
</template>

<script>
export default {
  name: "modalPhone",
  props: {
    currentId: Number,
    from: String,
  },
  data() {
    return {
      imgUrl: "",
      txt: "",
      id: this.currentId,
    };
  },
  methods: {
    closeModal() {
      this.$emit("closeModal", false);
      this.imgUrl = "";
      this.txt = "";
    },
    addMsg(){
        this.$emit("closeModal", false)
        
        let d = new Date(),
        H = d.getHours(),
        M = d.getMinutes(),
        D = ''
        
        if (M > 9) {
             D = H + ':' + M
        }else{
             D = H + ':0' + M
        }
        
        if (this.txt != "" && this.imgUrl != "" && this.from == "alex"){
            
            const item = {
                txt: this.txt,
                date: D,
                id: this.id++,
                from: 'alex',
                imgUrl:this.imgUrl,
            };
            this.$emit("addMsg", item);
            this.txt = this.imgUrl = "";
            
        }else if(this.txt != "" && this.imgUrl != "" && this.from == "evgen"){
            
            const item = {
                txt: this.txtTwo,
                date: D,
                id: this.id++,
                from: 'evgen',
                imgUrl:this.imgUrl,
            };
            this.$emit("addMsg", item);
            this.txt = this.imgUrl = "";
        }else{
            console.log('error');
             this.txt = this.imgUrl = "";
        }
    },
  }
};
</script>

<style>
</style>
