<template>
  <div>
      <div>
        <img
      :src="Poster"
      alt=""
    >
    <h2>
      {{ Title }}
    </h2>
    <h3>
      {{ Author }}
    </h3>
    <h4>
      {{ Year }}
    </h4>
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

</style>