<template>
  <div class="landing">
    <Jumbotron
      :actions="mainJumboActions"
      subtitle="Welcome to the"
      title="Pitbull Communicty"
      caption="A community-driven defi project with the anonymous developer
relinquishing ownership and burnt LP from the beginning of its creation."
      iframeUrl="https://www.youtube.com/embed/jqidVJnbkN0?rel=0&controls=1&autoplay=0&mute=0&start=0"
      backgroundImage="https://uploads-ssl.webflow.com/60959d4fca60f247be5ae078/6095a5590e5af96ce84e86a6_pitbull-bg.jpg"
    />

    <div class="landing__cards percentages container">
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

    <div class="landing__cards numbers container">
      <Numbers :num="0.212191" description="Price per Block" />
      <Numbers :num="0.211291" description="Price per Block" />
      <Numbers :num="9252092.613" description="Marketcap" />
      <Numbers :dollar="false" :num="100000000" description="Total Supply" />
      <Numbers :dollar="false" :num="5648974654132" description="Total Burnt" />
      <Numbers :dollar="false" :num="5913" description="Hodlers" />
    </div>

    <div class="landing__cards promotionals container">
      <Promotional
        title="Buy Tokens"
        logoName="dollar"
        description="Buy $PIT tokens via pancakeswap v1 with BNB. Gas fees are pennies! Copy our contract below."
      />

      <Promotional
        title="Hold it"
        logoName="hand"
        description="2% of each transaction will be distributed to all holders. Strong holder will watch their wallets grow!"
      />

      <Promotional
        title="Spread the Word"
        logoName="horn"
        description="Share, retweet, repost on all social media channels. Rock our cool merch and spread the pitbullish!"
      />
    </div>

    <Jumbotron
      :actions="secondaryJumboActions"
      subtitle="Security"
      title="Techrate Audit"
      caption="As half of total supply has been burnt into a dead address in the beginning and the liquidity pool has been burnt, it is impossible to modify Pitbull's contract for further changes."
      imageName="guard"
      backgroundImage="https://thumbs.dreamstime.com/z/white-dog-breed-pitbull-running-field-grass-wal-white-dog-breed-pitbull-running-field-grass-walk-117656984.jpg"
    />
    <ContactForm />
    <Footer />
  </div>
</template>

<script>
import Jumbotron from "@/components/compound/Jumbotron";
import Percentage from "@/components/cards/Percentage";
import Promotional from "@/components/cards/Promotional";
import Numbers from "@/components/cards/Numbers";
import ContactForm from "@/components/compound/ContactForm";
import Footer from "@/components/compound/Footer";

export default {
  name: "Home",
  components: {
    Jumbotron,
    Percentage,
    Numbers,
    Promotional,
    ContactForm,
    Footer,
  },
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
  padding-top: 80px;

  &__cards {
    padding: 1rem 0;
    display: grid;
    grid-gap: 2rem;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));

    div {
      margin: auto;
    }
  }
}
</style>
