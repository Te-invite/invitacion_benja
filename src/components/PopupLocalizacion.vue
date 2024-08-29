<script>
import Boton from './Boton.vue';
import PopupBase from './PopupBase.vue';
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
        mapUrl:'https://maps.app.goo.gl/RMnUo7bMcJN1auvZ9'
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
                src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d10590.848034586641!2d-60.1009674!3d-38.0265963!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x9592313fa2c85eff%3A0x5b1253cccbb79323!2sEstadio%20de%20Independencia!5e1!3m2!1ses-419!2sar!4v1724707269785!5m2!1ses-419!2sar" 
                width="300" height="200" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>

                <iframe class="map"
                src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3142.610837648265!2d-60.1006553241042!3d-38.03285107192159!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x9592311e20184ea5%3A0x9e747032d11e3a61!2sLa%20Cascada%20Eventos%20Adolfo%20Gonzales%20Chaves!5e0!3m2!1ses-419!2sar!4v1717480729319!5m2!1ses-419!2sar"
                width="300" height="200" style="border:0;" allowfullscreen="" loading="lazy"
                referrerpolicy="no-referrer-when-downgrade">
                </iframe>
            </div>
        </div>
        <template #footer>
            <Boton label="ABRIR APP" customClass="btn-mayor" @click="openMap()" />
        </template>
    </popup-base>
</template>

<style scoped> 

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