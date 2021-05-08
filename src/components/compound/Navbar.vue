<template>
  <div class="navbar container">
    <img src="../../assets/logo.png" class="navbar__img" />
    <div class="navbar__items">
      <ul>
        <li>One</li>
        <li>Two</li>
        <li>Three</li>
      </ul>
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

    ul {
      list-style: none;
      display: flex;

      li {
        margin: 0 0 0 0.5rem;
        color: white;
      }
    }
  }
}
</style>
