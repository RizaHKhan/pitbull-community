<template>
  <div class="footer-container">
    <div class="footer container">
      <h1 class="footer__header">Everyone Holds, Everyone Wins</h1>
      <div class="footer__links">
        <div
          class="footer__links--card"
          v-for="(link, index) in links"
          :key="index"
        >
          <h4>{{ link.title }}</h4>
          <p v-if="link.description">{{ link.description }}</p>
          <template v-if="link.pages">
            <router-link
              v-for="page in link.pages"
              :key="page.title"
              :to="page.to"
              >{{ page.title }}</router-link
            >
          </template>
        </div>
      </div>
      <div class="footer__company">
        <div class="footer__company--copyright"></div>
        <div class="footer__company--legal">
          <p>&#169;Copyright PitbullsBSC. All Rights Reserved</p>
          <div class="footer__company--legal--links">
            <router-link to="/">Legal Disclaimer</router-link>
            <router-link to="/">Risk Disclousure</router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          title: "Company",
          description:
            "Pitbull is a self-staking token abandoned by it's creator, raised by the community. Created on March 17,2021 on the Bibance Smart Chain network with contract renounced and Liquidity burnt, Pitbull has grown into a fully functional, decentrailized,. 100% community-driven project ",
        },
        {
          title: "Community",
          pages: [
            { title: "Discord", to: "/place" },
            {
              title: "Reddit",
              to: "/place",
            },
            {
              title: "Telegram",
              to: "/place",
            },
            {
              title: "Medium",
              to: "/place",
            },
          ],
        },
        {
          title: "Connect",
          pages: [
            { title: "Twitter", to: "/place" },
            {
              title: "Instagram",
              to: "/place",
            },
            {
              title: "TikTok",
              to: "/place",
            },
            {
              title: "Youtube",
              to: "/place",
            },
          ],
        },
        {
          title: "Resources",
          pages: [
            { title: "Pit Tracker Beta", to: "/place" },
            {
              title: "Pancake Swap",
              to: "/place",
            },
            {
              title: "Litepaper",
              to: "/place",
            },
            {
              title: "Team",
              to: "/place",
            },
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.footer {
  padding: 2rem 0;
  color: white;

  @include media-down(md) {
    padding: 2rem;
  }

  &__header {
    text-align: center;
    width: 80%;
    margin: auto;
    font-size: 3rem;

    @include media-up(md) {
      width: 40%;
    }
  }

  &__links {
    padding: 2rem 0;
    display: flex;
    grid-gap: 4rem;
    flex-wrap: wrap;
    justify-content: center;
    /* grid-template-columns: repeat(auto-fill, minmax(300px, 400px)); */

    h4 {
      color: #08b29f;
      margin: 1rem 0;
    }

    p {
      max-width: 400px;
    }

    a {
      color: white;
      text-decoration: none;
      display: block;
      margin: 0.5rem 0;
      transition: all 0.5s ease;

      &:hover {
        color: #08b29f;
      }
    }
  }
  &__company {
    padding-top: 2rem;
    border-top: 1px solid grey;

    &--legal {
      display: flex;
      justify-content: space-between;

      @include media-down(md) {
        text-align: center;
        flex-direction: column;

        p {
          margin: 1rem 0;
        }
      }

      &--links {
        a {
          color: white;
          text-decoration: none;
          margin-left: 1rem;
          transition: all 0.5s ease;

          &:hover {
            color: #08b29f;
          }
        }
      }
    }
  }
}
</style>
