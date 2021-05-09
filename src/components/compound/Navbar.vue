<template>
  <div class="navbar container">
    <img src="../../assets/logo.png" class="navbar__img" />
    <div class="navbar__items">
      <router-link to="/">Home</router-link>
      <router-link to="/team">Team</router-link>
      <router-link to="/Audit">Audit</router-link>
      <router-link to="/contact">Contact</router-link>
      <router-link to="/faq">FAQ</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style lang="scss" scoped>
.navbar {
  background: black;
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
    a {
      text-decoration: none;
      color: white;
      transition: all 0.5s ease;

      &:hover {
        color: #08b29f;
      }
    }
  }
}
</style>
