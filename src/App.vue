<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import axios from "axios";
import Main from "@/components/Main.vue";
import Header from "@/components/Header.vue";
export default {
  name: "App",
  data() {
    return {
      musics: [],
      generi: [],
      genere_selezionato: "",
    };
  },
  components: {
    Header: Header,
    Main: Main,
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        const response = res.data.response;
        this.musics = response;
        this.musics.forEach((music) => {
          if (!this.generi.includes(music.genre)) {
            this.generi.push(music.genre);
          }
        });
        this.musics.sort(function (music1, music2) {
          return parseInt(music2.year) - parseInt(music1.year);
        });
      });
  },
};
</script>
<style lang="scss">
@import "./components/scss/File.scss";
</style>
