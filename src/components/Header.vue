<template>
  <header>
    <div class="d-flex justify-content-between">
      <img class="logo" src="@/assets/logo.png" alt="logo" />
      <div class="selectGenere">
        <h3 class="h3">Seleziona il tuo genere</h3>
        <select class="opt" v-model="genere_selezionato">
          <option value="">Tutti i generi</option>
          <option v-for="genere in generi" :key="genere" :value="genere">
            {{ genere }}
          </option>
        </select>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped lang="scss">
header {
  background-color: #2e3a46;
  height: 70px;
  padding: 10px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  img {
    height: 50px;
  }
  .selectGenere {
    text-align: right;
    line-height: 25px;
    h3 {
      color: #fff;
    }
    .opt {
      width: 200px;
      height: 20px;
    }
  }
}
</style>