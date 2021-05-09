<template>
  <div class="landing">
    <Jumbotron
      :actions="mainJumboActions"
      subtitle="Welcome to the"
      title="Pitbull Communicty"
      caption="zA community-driven defi project with the anonymous developer
relinquishing ownership and burnt LP from the beginning of its creation."
      iframeUrl="https://www.youtube.com/embed/jqidVJnbkN0?rel=0&controls=1&autoplay=0&mute=0&start=0"
    />

    <Jumbotron
      :actions="secondaryJumboActions"
      subtitle="Security"
      title="Techrate Audit"
      caption="As half of total supply has been burnt into a dead address in the beginning and the liquidity pool has been burnt, it is impossible to modify Pitbull's contract for further changes."
      iframeUrl="https://www.youtube.com/embed/jqidVJnbkN0?rel=0&controls=1&autoplay=0&mute=0&start=0"
    />
  </div>
</template>

<script>
import Jumbotron from "@/components/compound/Jumbotron";

export default {
  name: "Home",
  components: { Jumbotron },
  computed: {
    mainJumboActions() {
      const actions = [];
      actions.push({ text: "Buy Now" });
      actions.push({ text: "Contract Address" });
      return actions;
    },
    secondaryJumboActions() {
      const actions = [];
      actions.push({ text: "See Audit" });
      return actions;
    },
  },
};
</script>

<style lang="scss" scoped></style>
