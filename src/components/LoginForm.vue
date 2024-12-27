<template>
  <form class="m-loginForm">
    <!-- Logo -->
    <div class="m-loginForm__logo">
      <img
        src="https://www.mfu.ac.th/fileadmin/_processed_/6/7/csm_logo_mfu_3d_colour_630b77d675.png"
        alt="MFU Logo"
      />
    </div>

    <!-- Header Component -->
    <Header :title="title" />

    <!-- Email Input -->
    <div class="m-loginForm__group">
      <animated-input placeholder="Email" animateBorder />
    </div>

    <!-- Password Input -->
    <div class="m-loginForm__group">
      <animated-input
        placeholder="Password"
        animateBorder
        inputType="password"
      />
    </div>

    <!-- Remember Me and Forgot Password -->
    <div class="m-loginForm__group -mg-lg">
      <div class="m-loginForm__rememberWrapper">
        <custom-checkbox
          name="remember_me"
          id="remember_me"
          labelText="Remember Me"
          checkbox="✔︎"
        ></custom-checkbox>

        <link-button href="#" linkText="Forgot Password"></link-button>
      </div>
    </div>

    <!-- Submit Button -->
    <submit-button>Login</submit-button>
  </form>
</template>

<script>
import Header from "./inputs/Header.vue";
import AnimatedInput from "./inputs/AnimatedInput.vue";
import CustomCheckbox from "./inputs/CustomCheckbox.vue";
import LinkButton from "./buttons/LinkButton.vue";
import SubmitButton from "./buttons/SubmitButton.vue";

export default {
  data() {
    return {
      email: "",
      password: "",
      rememberMe: false
    };
  },
  components: {
    Header,
    AnimatedInput,
    CustomCheckbox,
    LinkButton,
    SubmitButton
  },
  props: {
    title: String
  }
};
</script>

<style lang="scss" scoped>
@import "@/scss/components/forms/_loginForm.scss";

/* Logo styling */
.m-loginForm__logo {
  display: flex;
  justify-content: center;
  margin-bottom: 10px;

  img {
    max-width: 85px; /* Adjust width as necessary */
    height: auto;
  }
}
</style>
