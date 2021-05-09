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

    <div class="landing__cards percentages">
      <Percentage
        title="Reflection"
        :percent="2"
        description="Fee redistributed to all holders including black hole"
      />

      <Percentage
        title="Liquidity Accumulation"
        :percent="2"
        description="Fee on sell trades, added to the liquidity pool by smart contract locked forever"
      />

      <Percentage
        title="Burning"
        :percent="50"
        description="Burnt to the black hole, getting bigger from the fees."
      />
    </div>

    <Jumbotron
      :actions="secondaryJumboActions"
      subtitle="Security"
      title="Techrate Audit"
      caption="As half of total supply has been burnt into a dead address in the beginning and the liquidity pool has been burnt, it is impossible to modify Pitbull's contract for further changes."
      imageName="guard"
    />
  </div>
</template>

<script>
import Jumbotron from "@/components/compound/Jumbotron";
import Percentage from "@/components/cards/Percentage";

export default {
  name: "Home",
  components: { Jumbotron, Percentage },
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

<style lang="scss" scoped>
.landing {
  &__cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
