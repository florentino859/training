<template>
    <div  :class="[bgColor,txtColor]" class="Producto">
        <div>{{producto.name}}</div>
        <div>{{producto.price}}</div>
        <button @click="func(producto.price)">Agregar Carrito</button>
    </div>
</template>
<script>
    export default {
        name: "ProductItem"  ,
        props:{
            producto: Object,
            func: Function
        },
        data(){
            return{
                bgColor:"bgColor",
                txtColor:"txtColor"
            }
        },
        methods:{
            CambiarColor(){
                    this.bgColor = 'bgColorAzul';
            }
        }
    }
</script>

<style scoped>
    ul{
        list-style: disc;
    }

    .bgColor{
        background-color: #42b983;
    }

    .bgColorAzul{
        background-color: blue;
    }
</style>

