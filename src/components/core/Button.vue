<template>
  <button class="button" @click="$emit('click')">{{ text }}</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: {
      type: String,
      default: "Submit",
    },
  },
};
</script>

<style lang="scss" scoped>
.button {
  margin-right: 11px;
  padding: 0.5rem 3rem;
  border-style: solid;
  border-width: 1px;
  border-color: rgba(255, 255, 255, 0.4);
  border-radius: 20px;
  background-color: rgba(8, 179, 159, 0);
  box-shadow: none;
  -webkit-transition: background-color 425ms ease;
  transition: background-color 425ms ease;
  font-family: Raleway, sans-serif;
  color: #fff;
  font-weight: 700;
  text-align: center;

  &:hover {
    cursor: pointer;
    background-color: #08b29f;
    box-shadow: 4px 4px 11px 2px rgba(255, 255, 255, 0.4);
    color: white;
  }
}
</style>
