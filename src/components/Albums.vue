<template>
  <div>
    <div class="music">
        <img class="album-music"
      :src="Poster"
      alt=""
    >
    <span class="title">
      {{ Title }}
    </span>
    <span class="author"> {{ Author }}
    </span>
    <span class="year">
      {{ Year }}
    </span>
  </div>
  </div>
</template>

<script>
export default {
    name: 'Albums',
    props: [
        'Poster',
        'Title',
        'Author',
        'Year'
    ]
}
</script>

<style>
    .music {
        width: 160px;
        height: 250px;
        text-align: center;
        background-color: #2E3A46;
        
    }

    .album-music {
        width: 150px;
        height: 150px;
    }

    span {
        display: block;
        font-size: 1em;
        color: white;
    }

    .title {
        font-size: 1.1em;
        font-weight: bold;
    }

    .author, .year {
        color: lightgray;
        font-size: 0.8em;
    }

</style>