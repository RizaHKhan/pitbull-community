<template>
  <div
    class="jumbotron"
    :style="{ backgroundImage: 'url(' + backgroundImage + ')' }"
  >
    <div class="jumbotron__left">
      <p class="jumbotron__left--subtitle">{{ subtitle }}</p>
      <h1 class="jumbotron__left--title">{{ title }}</h1>
      <p class="jumbotron__left--caption">{{ caption }}</p>
      <div class="jumbotron__left--actions" v-if="actions.length">
        <Button :text="action.text" v-for="(action, id) in actions" :key="id" />
      </div>
    </div>
    <div class="jumbotron__right">
      <iframe v-if="iframeUrl" :src="iframeUrl" frameborder="0"></iframe>
      <img v-if="imageName" :src="imgUrl" />
    </div>
  </div>
</template>

<script>
import Button from "@/components/core/Button";

export default {
  name: "Jumbotron",
  components: { Button },
  props: {
    subtitle: {
      type: String,
      default: "",
    },
    title: {
      type: String,
      default: "",
    },
    caption: {
      type: String,
      default: "",
    },
    iframeUrl: {
      type: String,
      default: "",
    },
    imageName: {
      type: String,
      default: "",
    },
    actions: {
      type: Array,
      default: () => [],
    },
    backgroundImage: {
      type: String,
      default: "",
    },
  },
  computed: {
    imgUrl() {
      return require(`../../assets/images/${this.imageName}.png`);
    },
  },
};
</script>

<style lang="scss" scoped>
.jumbotron {
  background-position: 0px 0px, 50% 50%;
  background-size: auto, cover;
  background-attachment: fixed;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  padding: 4rem 0.5rem;

  @include media-down(lg) {
    grid-template-columns: 1fr;
  }

  &__left {
    &--title {
      font-size: 4rem;
    }

    &--actions {
      display: flex;
      grid-gap: 0.2rem;
    }
  }

  &__right {
    iframe {
      width: 100%;
      height: 100%;
      box-shadow: 1px 1px 14px 5px rgba(0, 0, 0, 0.44);
    }
  }
}
</style>
