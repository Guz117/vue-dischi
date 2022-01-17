<template>
  <main>
    <div class="album">
        <Albums 
            v-for="(album, index) in albums"
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
export default {
    name:'Main',
    data() {
        return {
            albums: null,
        }
    },
    components: {
        Albums,
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
    }
}
</script>

<style>
    main {
        width: 100%;
        height: 100vh;
        margin: 0 auto;
        background-color: #1E2D3B;
    }
    .album {
        width: calc((100% / 2) - 10px);
        margin:0 auto;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        gap: 10px;
        padding-top: 3em;
    }
</style>