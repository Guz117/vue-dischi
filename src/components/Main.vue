<template>
  <main>
    <div>
        <Search
            @doSearch="searchGenre($event)"
        />
    </div>      
    <div class="album">
        <Albums 
            v-for="(album, index) in filteredAlbum"
            :key="index"
            :Poster="album.poster"
            :Title="album.title"
            :Author="album.author"
            :Year="album.year"
        />
    </div>     
  </main>
</template>

<script>
import axios from 'axios';
import Albums from './Albums';
import Search from './Search';

export default {
    name:'Main',
    components: {
        Albums,
        Search,
    },
    data() {
        return {
            albums: null,
            textSearch: '',
        }
    },
    computed: {
        filteredAlbum() {
            if (this.textSearch === '') {
                return this.albums;
            }
            return this.albums.filter((element) => element.genre.toLowerCase().includes(this.textSearch.toLowerCase()))
        }
    },
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((result) => {
            console.log(result);
            this.albums = result.data.response;
        })
        .catch ((error) => {
            console.log(error)
        })
    },
    methods: {
        searchGenre(text) {
            console.log(text);
            this.textSearch = text;
        }
    }
}
</script>

<style lang="scss">
    main {
        width: 100%;
        height: 100vh;
        margin: 0 auto;
        background-color: #1E2D3B;
    }
    .album {
        width: 70%;
        margin:0 auto;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        gap: 10px;
        padding-top: 3em;
    }
</style>