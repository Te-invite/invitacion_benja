<script>
export default{
    name:'Boton',
    props: {
    label: {
      type: String,
      required: false 
    },
    customClass: {
      type: String,
      default: 'btn-mayor'
    }
  }

}
</script>
<template>
   <button type="button" :class="['btn', customClass, 'btn-lg']">
      {{ label }}
    </button>
</template>
<style>
.btn-mayor{
    background: transparent;
    color:#F43722;
    border: 2px solid var(--color-font-secondar);
    font-family:Montserrat;
    font-weight: 500;
    font-size: 1rem;
    padding: 1rem 2rem;
}
.btn-mayor:hover{
    background:transparent;
    color:#F43722;
}
.btn-mayor:focus,
.btn-mayor:active {
    outline: none;
}


</style>