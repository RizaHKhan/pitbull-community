<template>
  <div class="social-media container">
    <font-awesome-icon :icon="['fab', 'instagram']" />
    <font-awesome-icon :icon="['fab', 'discord']" />
    <font-awesome-icon :icon="['fab', 'twitter']" />
  </div>
</template>

<script>
export default {
  name: "SocialMediaIcons",
};
</script>

<style lang="scss" scoped>
.social-media {
  display: flex;
  grid-gap: 1rem;
  justify-content: flex-end;
  font-size: 1.75rem;
  color: white;

  svg {
    transition: transform 0.5s ease;
    &:hover {
      cursor: pointer;
      transform: scale(1.2);
    }
  }
}
</style>
