<template>
    <div>
        <ul id="menu">
            <li v-for="num in numeros" :key="num">
                <router-link :to="'/tabla/' + num">
                    Tabla {{ num }} | 
                </router-link>
            </li>
        </ul>

    </div>
</template>

<script>
    export default {
        name: "MenuTablaMultiplicar", 
        data() {
            return{
                numeros: []
            }
        },
        mounted() {
            for (var i = 1; i <= 5; i++){
                let random = parseInt(Math.random() * 100) + 1;
                this.numeros.push(random);
            }
        }
    }
</script>

<style>
    ul#menu li {
        display: inline;
    }
</style>

