<template>
    <div>
        <ul id="menu">
            <li>
                <router-link to="/">Deportes</router-link> | 
            </li>
            <li>
                <router-link to="/comics">Comics</router-link> | 
            </li>
            <li>
                <router-link to="/numeros">Números</router-link> | 
            </li>
            <li>
                <router-link to="/numerodoble">Doble SIN</router-link> | 
            </li>
            <li>
                <router-link to="/numerodoble/77">Doble 77</router-link>
            </li>            
        </ul>
    </div>
</template>

<script>
    export default {
        name: "MenuComponent"
    }
</script>

<style>
    ul#menu li {
        display: inline;
    }
</style>
