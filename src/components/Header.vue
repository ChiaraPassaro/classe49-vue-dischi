<template>
  <header class="d-flex justify-content-between ps-3 pe-3">
    <div>
      <img
        src="../assets/img/spotify-logo.png"
        alt="Spotify"
      >
    </div>
    <div>
      <select
        v-model="valueSelect"
        class="form-select mt-3"
        @change="$emit('changeGenre', valueSelect)"
      >
        <option value="">
          Seleziona un genere
        </option>
        <option
          v-for="(genre, index) in genres"
          :key="index"
          :value="genre"
        >
          {{ genre }}
        </option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    genres: {
      type: Array,
    },
  },
  data() {
    return {
      valueSelect: '',
    };
  },
};
</script>

<style lang="scss">
header {
    height: 70px;
    background-color: #2e3a46;
    line-height: 70px;
    img {
        width: 50px;
    }
}
</style>
