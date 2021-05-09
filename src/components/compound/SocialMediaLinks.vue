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
  position: fixed;
  width: 100%;
  top: 0;
  height: 40px;
  display: flex;
  grid-gap: 1rem;
  justify-content: flex-end;
  align-content: center;
  font-size: 1.75rem;
  color: white;
  background: #333;
  padding: 0.5rem;

  svg {
    transition: transform 0.5s ease;
    margin: auto 0;
    &:hover {
      cursor: pointer;
      transform: scale(1.2);
    }
  }
}
</style>
