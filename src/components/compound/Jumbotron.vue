<template>
  <div class="jumbotron">
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
      <img v-if="imageUrl" :src="imageUrl" />
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
    imageUrl: {
      type: String,
      default: "",
    },
    actions: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style lang="scss" scoped>
.jumbotron {
  background-color: grey;
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
    }
  }
}
</style>
