<template>
  <div class="card p-3 text-center border-0">
    <div class="p-3">
      <img
        class="img-fluid mb-3"
        :src="srcImage"
        :alt="altImage"
      >
      <p class="title text-uppercase fw-bold">
        {{ title }}
      </p>
      <p class="subtitle lead mb-0">
        {{ subtitle }}
      </p>
      <p class="small">
        {{ small }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    srcImage: {
      type: String,
    },
    altImage: {
      type: String,
    },
    title: {
      type: String,
    },
    subtitle: {
      type: String,
    },
    small: {
      type: String,
    },
  },
};
</script>

<style lang="scss">
.card {
  background-color: transparent !important;
  div {
    background-color: #2e3a46;
    height: 100%;
  }
  .subtitle,
  .small {
    color: #7d7977;
  }
}
</style>
