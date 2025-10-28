<template>
    <div>
        <h2>Padre comics</h2>
        <div>
            <form v-on:submit.prevent="createComic()">
                <label>Titulo</label>
                <input type="text" v-model="comicForm.titulo"/>
                <label>Imagen</label>
                <input type="text" v-model="comicForm.imagen"/>
                <label>Descripción</label>
                <input type="text" v-model="comicForm.descripcion"/>
                <label>Año</label>
                <input type="number" v-model="comicForm.year"/>
                <button>
                    Nuevo comic
                </button>
            </form>
        </div>
        <div v-if="comicFavorito" style="background-color: lightgray;">
            <h6>{{ comicFavorito.titulo }}</h6>
            <img :src="comicFavorito.imagen"/>
        </div>
        <div id="comics" v-for="(comic, index) in comics" :key="comic">
            <ComicComponent :comic="comic" :index="index"
            v-on:seleccionarFavorito="seleccionarFavorito"
            v-on:deleteComic="deleteComic"/>
        </div>
    </div>
</template>

<script>
import ComicComponent from './ComicComponent.vue';

    export default {
        name: "ComicsComponent", 
        components: {
            ComicComponent
        }, methods: {
            seleccionarFavorito(comic) {
                console.log(comic.titulo);
                this.comicFavorito = comic;
            }, createComic() {
                this.comics.push(this.comicForm);
            }, deleteComic(index) {
                this.comics.splice(index, 1);
            }
        },
        data() {
            return {
                comicForm: {
                    titulo: "",
                    imagen: "", 
                    descripcion: "",
                    year: 0
                },
                comicFavorito: null,
                comics: [
                    {
                        titulo: "Spiderman",
                        imagen:
                            "https://3.bp.blogspot.com/-i70Zu_LAHwI/T290xxduu-I/AAAAAAAALq8/8bXDrdvW50o/s1600/spiderman1.jpg",
                        descripcion: "Hombre araña"
                        , year: 1997
                    },
                    {
                        titulo: "Wolverine",
                        imagen:
                            "https://images-na.ssl-images-amazon.com/images/I/51c1Q1IdUBL._SX259_BO1,204,203,200_.jpg",
                        descripcion: "Lobezno"
                        , year: 2003
                    },
                    {
                        titulo: "Guardianes de la Galaxia",
                        imagen:
                            "https://comicstores.es/imagenes/9772938/977293843900900006.JPG",
                        descripcion: "Yo soy Groot"
                        , year: 2006
                    },
                    {
                        titulo: "Avengers",
                        imagen:
                            "https://d26lpennugtm8s.cloudfront.net/stores/057/977/products/ma_avengers_01_01-891178138c020318f315132687055371-640-0.jpg",
                        descripcion: "Los Vengadores"
                        , year: 1993
                    },
                    {
                        titulo: "Spawn",
                        imagen:
                            "https://i.pinimg.com/originals/e1/d8/ff/e1d8ff4aeab5e567798635008fe98ee1.png",
                        descripcion: "Al Simmons"
                        , year: 2000
                    },
                    {
                        titulo: "Batman",
                        imagen:
                            "https://www.comicverso.com/wp-content/uploads/2020/06/The-Killing-Joke-657x1024.jpg",
                        descripcion: "Murcielago"
                        , year: 2001
                    }
                ]

            }
        }
    }
</script>