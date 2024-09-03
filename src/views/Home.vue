<script>
import titulo from '@/assets/img/title.png';
import Boton from '@/components/Boton.vue';
import coco from '@/assets/img/coco2.png';
export default {
    name:'Home',
    components:{
        Boton,
    },
    data(){
        return{
            titulo,
            coco
        }
    },
    methods: {
        enterInvitation() {
            console.log("Botón clickeado");
            this.$router.push({ name: 'invitacion' });
        }
    }

}
</script>
<template>
    <div class="home_conteiner">
        <div class="home_content">
            <img :src="titulo" class="img__title" alt="titulo">
        </div>
        <Boton label="INGRESAR" customClass="btn-mayor" class="btn-ingresar" @click="enterInvitation()"/>
        <div class="img_principal_content">
            <img :src="coco" class="img_coco2"  alt="coco">
        </div>
    </div>
</template>
<style scoped>
.home_conteiner{
    position: static;
    top: 0;
    left: 0;
    width: 100%;
    min-height: 100vh;
    background-image: url('../assets/img/fondo.png'); 
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    z-index: -2;
}
.home_conteiner{
    width:100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content:flex-end;
    align-items:center;
}
.home_content{
    margin-bottom:1.5rem;
    width:270px;
    height:120px;
    position:relative;
}
.img__title{
    position: absolute;
    width: 100%;
    height:auto;
}
.btn-ingresar{
    position:relative;
    z-index: 100;
}
.img_principal_content{
    width: 280px;
    height:300px;
    position:relative;
    margin-top: 2rem;
}
.img_coco2{
    position:absolute;
    width: 100%;
    height:100%;
    bottom: 0;
    left: 0;
}
</style>