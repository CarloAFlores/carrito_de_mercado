<template>
<div class="col-12 col-sm-4 col-md-3 col-lg-2 mb-3 mb-3">
    <div class="card">
        <img :src="producto.image" :alt="`imagen-${producto.name}`" class="card-img-top">
        <div class="card-body">
            <h5 class="card-title">{{producto.name}}</h5>
            <p class="card-text">$<span>{{producto.status}}</span></p>
            <button class="btn btn-dark" @click="agregar(producto)">Comprar</button>

        </div>
    </div>
</div>
</template>

<script>
import { useStore } from "vuex";
export default {
    props:['producto'],
    setup(){
        const store = useStore()
        const agregar = producto => {
            store.dispatch('agregarAlCarro', producto)
        }
        return{agregar}
    }

}
</script>

<style>

</style>