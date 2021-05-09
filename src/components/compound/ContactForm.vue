<template>
  <div class="contact-form">
    <img class="contact-form__img" src="../../assets/images/envelope.png" />
    <h1>Contact Us</h1>
    <p>
      For all business enquires, please use the form below toget in touch with
      us
    </p>
    <form class="contact-form__form">
      <label for="name">Name</label>
      <input type="text" name="name" />
      <label for="email">Email</label>
      <input type="email" name="email" />
      <textarea placeholder="Ask us a question..." />
      <Button text="Submit" />
    </form>
  </div>
</template>

<script>
import Button from "@/components/core/Button";
export default {
  name: "ContactForm",
  components: { Button },
};
</script>

<style lang="scss" scoped>
.contact-form {
  max-width: 350px;
  margin: auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  color: white;
  text-align: center;

  &__img {
    width: 70px;
    margin: auto;
  }

  &__form {
    display: flex;
    grid-gap: 1rem;
    flex-direction: column;

    label {
      color: white;
    }

    input {
      color: white;
      background: 0;
      border: 0;
      border-bottom: 1px solid grey;
    }

    textarea {
      color: white;
      background: 0;
      border: solid 1px grey;
    }
  }
}
</style>
