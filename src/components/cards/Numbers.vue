<template>
  <div class="numbers">
    <h1 class="numbers__num">
      {{ dollar ? "$" : "" }}{{ num.toLocaleString() }}
    </h1>
    <p class="numbers__description">{{ description }}</p>
  </div>
</template>

<script>
export default {
  props: {
    num: {
      type: Number,
      default: 0,
    },
    description: {
      type: String,
      default: "",
    },
    dollar: {
      type: Boolean,
      default: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.numbers {
  padding: 0.5rem;
  display: flex;
  border-radius: 5px;
  flex-direction: column;
  text-align: center;
  transition: all 0.5s ease;
  width: 275px;
  color: white;
  transition: all 0.5s ease;
  background-color: rgba(20, 20, 20, 0.8);

  &:hover {
    background-color: rgba(20, 20, 20, 1);
  }

  &__title {
    margin: auto;
    padding-bottom: 0.75rem;
    border-bottom: 1px solid grey;
    text-transform: uppercase;
  }
  &__num {
    color: #1ac6b8;
    font-size: 1.5rem;
  }
  &__description {
    width: 80%;
    margin: auto;
  }

  &:hover {
    box-shadow: 1px 1px 17px 0 rgba(0, 0, 1, 0.72);
  }
}
</style>
