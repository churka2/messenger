<template>
<div class="messenger__wrap">
  <div class="container">
    <div class="phone__wrap">
        <div class="phone__head">
            <img src="@/assets/img/alex.svg" alt="">
            <div class="phone-one-head__txt head__txt">
                <p class="head__name ">Александр</p>
                <p class="head__status ">Онлайн</p>
            </div>
        </div>
        
        <div class="phone-one__display phone__display">
            
        </div>
        
        <div class="phone-one__bottom phone__bottom">
            <input type="text" class="bottom__input" placeholder="Написать сообщение...">
            <button class="camera__btn"><img src="../assets/img/camera.svg" alt="" class="camera__img"></button>
        </div>
    </div>
  </div>
  
   <div class="container">
    <div class="phone__wrap">
        <div class="phone__head">
            <img src="@/assets/img/jenya.svg" alt="">
            <div class="phone-one-head__txt head__txt">
                <p class="head__name ">Евгений</p>
                <p class="head__status ">Онлайн</p>
            </div>
        </div>
        
        <div class="phone-one__display phone__display">
            
        </div>
        
        <div class="phone-one__bottom phone__bottom">
            <input type="text" class="bottom__input" placeholder="Написать сообщение...">
            <button class="camera__btn"><img src="../assets/img/camera.svg" alt="" class="camera__img"></button>
        </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name:'HeaderMessenger'
}
</script>