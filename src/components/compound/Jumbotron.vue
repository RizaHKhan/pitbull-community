<template>
  <div
    class="jumbotron_container"
    :style="{ backgroundImage: 'url(' + backgroundImage + ')' }"
  >
    <div class="jumbotron container">
      <div class="jumbotron__left">
        <p class="jumbotron__left--subtitle">{{ subtitle }}</p>
        <h1 class="jumbotron__left--title">{{ title }}</h1>
        <p class="jumbotron__left--caption">{{ caption }}</p>
        <div class="jumbotron__left--actions" v-if="actions.length">
          <Button
            :text="action.text"
            v-for="(action, id) in actions"
            :key="id"
          />
        </div>
      </div>
      <div class="jumbotron__right">
        <iframe v-if="iframeUrl" :src="iframeUrl" frameborder="0"></iframe>
        <img v-if="imageName" :src="imgUrl" />
      </div>
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
.jumbotron_container {
  background-position: 0px 0px, 50% 50%;
  background-size: auto, cover;
  background-attachment: fixed;
  background-color: rgba(0, 0, 0, 0.8);
  background-blend-mode: darken;
}
.jumbotron {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  padding: 4rem 0.5rem;
  color: white;

  @include media-down(lg) {
    grid-template-columns: 1fr;
  }

  &__left {
    @include media-down(md) {
      text-align: center;
    }
    &--title {
      font-size: 4rem;
      margin: 2rem 0;
    }

    &--actions {
      display: flex;
      grid-gap: 0.2rem;
      margin: 2rem 0;
      @include media-down(md) {
        justify-content: center;
      }
    }
  }

  &__right {
    display: flex;
    iframe {
      width: 100%;
      height: 100%;
      box-shadow: 1px 1px 14px 5px rgba(0, 0, 0, 0.44);
    }

    img {
      max-width: 200px;
      margin: auto;
    }
  }
}
</style>
