<template>
  <div id="app">
    <div class="nav">
      <div class="nav__social-media-links">
        <SocialMediaLinks />
      </div>
      <div class="nav__navbar">
        <Navbar />
      </div>
    </div>
    <div class="container">
      <router-view />
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/compound/Navbar";
import SocialMediaLinks from "@/components/compound/SocialMediaLinks";

export default {
  name: "App",
  components: { Navbar, SocialMediaLinks },
};
</script>

<style lang="scss">
#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  .nav {
    &__social-media-links {
      background: red;
    }

    &__navbar {
      background: black;
    }
  }
}
</style>
