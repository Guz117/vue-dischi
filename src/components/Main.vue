<template>
  <main>
      <div class="row">
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

</style>