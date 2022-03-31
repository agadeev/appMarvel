<template>
    <div id="app">

        <app-header/>

        <div class="container">
            <h1 class="pt-3 pb-3">Персонажи Marvel</h1>

            <app-modal :character = "characters[characterIndex]"/>

            <spinner/>

        <!-- Heroes Card-->
            <div class="row row-cols-1 row-cols-md-4 g-4">
                <div v-for="(el,idx) in characters" :key="el.id" class="col"> 
                    <div class="card">
                        <div>
                          <img :src="el.thumbnail" class="card-img-top" :alt="el.name">
                        </div>
                        <div class="card-body">
                            <h5 class="card-title">{{el.name}}</h5>
                            <p class="card-text">{{el.description}}</p>   
                            <button 
                            type="button" 
                            class="btn btn-danger" 
                            data-bs-toggle="modal"
                            data-bs-target="#exampleModal"
                            @click="characterIndex = idx"
                            >Подробнее</button>
                        </div>
                    </div>
                </div>
            </div>
        <!-- -->

        </div>
    </div>
</template>

<script>
    import Spinner from "./components/Spinner";
    import AppModal from "./components/AppModal";
    import AppHeader from "./components/AppHeader";

    export default {
        name: 'App',
        components: {
            AppHeader,
            AppModal,
            Spinner,
        },
        data() {
            return {
                loading: false,
                characters: [],
                characterIndex: 0,
            }
        },
        methods: {
            fetchCharacters: function(){
                return fetch ('https://netology-api-marvel.herokuapp.com/characters') 
                    .then(res => res.json())
                    .then(json => this.characters = json)
            }
        },
        computed: {},
        mounted() {
            this.fetchCharacters() 
        },
    }
    
</script>

<style>
    .card .card-body .card-text {
        text-overflow: ellipsis;
       overflow: hidden;
       -webkit-line-clamp: 4;
       display: -webkit-box;
       word-wrap: break-word;
       -webkit-box-orient: vertical;
       line-height: 1.4;
       font-size: 0.9rem;
    }
</style>
