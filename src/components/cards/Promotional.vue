<template>
  <div class="promotional">
    <h2 class="promotional__title">{{ title }}</h2>
    <img class="promotional__logo" :src="logoUrl" />
    <p class="promotional__description">{{ description }}</p>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "",
    },
    logoName: {
      type: String,
      default: "",
    },
    description: {
      type: String,
      default: "",
    },
  },
  computed: {
    logoUrl() {
      return require(`@/assets/images/${this.logoName}.png`);
    },
  },
};
</script>

<style lang="scss" scoped>
.promotional {
  padding: 0.5rem;
  display: flex;
  border-radius: 5px;
  flex-direction: column;
  text-align: center;
  transition: all 0.5s ease;
  width: 275px;
  color: white;

  &__title {
    margin: auto;
  }
  &__logo {
    height: 50px;
    object-fit: contain;
  }
  &__description {
    width: 80%;
    margin: auto;
  }

  &:hover {
    box-shadow: 1px 1px 17px 0 rgba(0, 0, 1, 0.72);
  }
}
</style>
