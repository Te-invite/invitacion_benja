<script>
import PopupBase from './PopupBase.vue';
import Boton from './Boton.vue';
export default {
    components: { 
        PopupBase,
        Boton
    },
    data() {
        return {
        infoBtn: '¿CÓMO LLEGAR?',
        modalTitle: 'Cómo llegar a la Fiesta',
        map: 'ABRIR APP',
        mapUrl:'https://maps.app.goo.gl/f2j4PYsgmVTJ1P6QA'
        };
    }, 
    methods:{
        openMap(){
            window.open(this.mapUrl, '_blank');
        }   
    }
};
</script>
<template>
    <popup-base :title="modalTitle" >
        <div class="modal-body">
            <div class="map-container">
                <iframe class="map" 
                src="https://www.google.com/maps/embed?pb=!1m17!1m12!1m3!1d2649.854893578286!2d-60.414899000000005!3d-37.967261!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m2!1m1!2zMzfCsDU4JzAyLjEiUyA2MMKwMjQnNTMuNiJX!5e1!3m2!1ses-419!2sar!4v1725047778328!5m2!1ses-419!2sar" 
                width="200" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade">
            </iframe>
            </div>
        </div>
        <template #footer>
            <Boton label="ENCENDER GPS" customClass="btn-mayor" @click="openMap()" />
        </template>
    </popup-base>
</template>

<style scoped> 
.map-container{
    margin-bottom:1rem;
}
.map{
    width:240px;
    height:100px;
}
@media(max-width:320px) {   
    

    .map{
        margin-top:2rem;
        width:200px;
    }
}

@media(max-width:360px) {
    
    .circle{
        width: 45px;
        height:45px;
    }
    
    
}
@media (min-width: 768px) and (max-width: 991px){
    
    .btn-primary{
        width:60%;
    }
}
@media (min-width: 1025px) {
    
    
    .circle{
        width: 90px;
        height:90px;
    }
    .pop-up-footer{
        width:100%;
    }
    .btn-primary{
        width:50%;
    }
}

</style>