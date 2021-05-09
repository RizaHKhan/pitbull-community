<template>
  <div class="navbar container">
    <img src="../../assets/images/logo.png" class="navbar__img" />
    <div class="navbar__items" :class="menuOpen ? 'open' : ''">
      <router-link to="/">Home</router-link>
      <router-link to="/team">Team</router-link>
      <router-link to="/Audit">Audit</router-link>
      <router-link to="/contact">Contact</router-link>
      <router-link to="/faq">FAQ</router-link>
    </div>
    <div class="navbar__burger-container" @click="menuOpen = !menuOpen">
      <div :class="menuOpen ? 'ex-close' : 'ex'"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      menuOpen: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.navbar {
  background: black;
  position: relative;
  display: flex;
  justify-content: space-between;
  align-content: center;

  &__img {
    height: 50px;
    width: 50px;
  }

  &__items {
    margin: auto 0;
    display: flex;
    grid-gap: 1rem;

    @include media-down(md) {
      max-height: 0px;
      position: absolute;
      width: 100%;
      top: 58px;
      overflow: hidden;
      transition: all 0.5s ease;
      background: black;
      justify-content: center;
    }

    @include media-down(sm) {
      flex-direction: column;
      text-align: center;
    }

    a {
      text-decoration: none;
      color: white;
      transition: all 0.5s ease;

      &:hover {
        color: #08b29f;
      }
    }
  }

  &__burger-container {
    display: none;

    &:hover {
      cursor: pointer;
    }

    @include media-down(md) {
      display: flex;
      height: 20px;
    }
    margin: auto 0;
  }
}

.open {
  max-height: 1000px;
}
</style>
