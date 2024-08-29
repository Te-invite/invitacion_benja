<script>
import titulo from '@/assets/img/title.png';
import Boton from '@/components/Boton.vue';
import coco from '@/assets/img/coco2.png';
import Spinner from '@/components/Spinner.vue';
export default {
    name:'home',
    components:{
        Boton,
        Spinner
    },
    data(){
        return{
            titulo,
            coco
        }
    },methods:{
        enterInvitation(){
            this.$router.push({
                name: 'invitacion'
            });
        }
    }
}
</script>
<template>
   <div class="home_container box">
    <Spinner/>
        <div class="container__title">
            <img :src="titulo" class="img__title" alt="titulo">
        </div>
        <Boton label="INGRESAR" customClass="btn-mayor" @click="enterInvitation"/>
        <div class="img_principal_content">
            <div class="container__img">
            <img :src="coco" class="img_coco2" alt="coco">
        </div>
        </div>
        <Spinner/>
    </div>
  </template>
  
<style>
.home_container{
    width: 100%;
    height: 100vh;
    background-image: url(../assets/img/fondo.png);
    background-repeat: no-repeat;
    background-size: cover;
    overflow: hidden;
}
.box{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.container__title{
    width:350px;
    height:auto;
    display:flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.img__title{
    width: 100%;
    height: auto;
}
.img_principal_content{
    width:100%;
    position:absolute;
    bottom: 0;
    left: 20%;
}
.container__img{
    width:270px;
    height:auto;
    display: flex;
    justify-content: center;
    align-items: center;    
}
.img_coco2{
    width:100%;
    height: auto;
}

</style>