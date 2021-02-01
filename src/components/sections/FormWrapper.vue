<template>
  <div class="form-wrapper">
    <a href="/" class="form-wrapper__logo">
      <img
        lass="form-wrapper__logo-img"
        src="../../assets/logo-text.png"
        alt="logo"
      />
    </a>
    <span class="form-wrapper__title">Sign in</span>
    <span class="form-wrapper__subtitle"
      >Don’t have an account?
      <a href="#" class="form-wrapper__subtitle-link">Sign up now</a></span
    >
    <the-form />
    <the-footer />
  </div>
</template>

<script>
import TheFooter from "../TheFooter.vue";
import TheForm from "../TheForm.vue";
export default {
  components: { TheForm, TheFooter },
  name: "FormWrapper",
};
</script>
<style lang="scss">
.form-wrapper {
  @include flex(start, start, column);
  padding: 50px 0;
  @media screen and (max-width: 1440px) {
    padding: 0;
  }
  &__logo {
    position: relative;
    margin-bottom: 112px;
    max-width: 251px;
    img {
      position: absolute;
      top: 0;
      bottom: 0;
      right: 0;
      left: 0;
      max-width: 251px;
    }
  }

  &__title {
    @include text($h28, 700, $black);
    margin-bottom: 15px;
  }
  &__subtitle {
    @include text($h14, 600, $black);
    margin-bottom: 61px;
  }
  &__subtitle-link {
    padding-left: 10px;
  }
  .the-form {
    margin-bottom: 119px;
    @media screen and (max-width: 1440px) {
      margin-bottom: 20px;
    }
  }
}
</style>