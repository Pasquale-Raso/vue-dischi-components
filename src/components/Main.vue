<template>
  <section id="album-container">
    <div v-for="(music, index) in musics" :key="music" class="card">
      <div
        v-if="genere_selezionato == '' || genere_selezionato == music.genere"
      >
        <img :src="musics[index].poster" />
        <h2 class="title">{{ musics[index].title }}</h2>
        <address class="author">{{ musics[index].author }}</address>
        <time class="year">{{ musics[index].year }}</time>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Main",
  data() {
    return {};
  },
};
</script>

<style>
#album-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

#album-container .card {
  background-color: #2e3a46;
  padding: 20px;
  margin: 20px;
  flex-basis: 200px;
  text-align: center;
  min-height: 350px;
}

#album-container .card img {
  width: 100%;
  height: auto;
}

#album-container .card .title {
  color: #fff;
  margin: 15px 0;
}
#album-container .card .author,
#album-container .card .year {
  color: #808080;
  font-size: 21px;
}
#album-container .card .year {
  font-size: 16px;
}
</style>