<template>
  <div class="tabs-wrapper">
    <img
      class="tabs-wrapper__vektor top"
      src="../../assets/VectorTop.png"
      alt="vector"
    />
    <img
      class="tabs-wrapper__vektor bottom"
      src="../../assets/vector.png"
      alt="vector"
    />
    <the-tabs />
    <the-burger />
  </div>
</template>
<script>
import TheBurger from "../TheBurger.vue";
import TheTabs from "../TheTabs.vue";
export default {
  components: { TheTabs, TheBurger },
  name: "TabsWrapper",
};
</script>
<style lang="scss">
.tabs-wrapper {
  @include flex(center, center);
  flex: 1;
  background-color: $button-blue;
  max-width: 798px;
  position: relative;
  border-radius: 15px;
  overflow: hidden;
  @media screen and (max-width: 1110px) {
    min-width: calc((100% / 24) * 12);
  }
  @media screen and (max-width: 1100px) {
    min-width: 100%;
  }

  &__vektor {
    position: absolute;
    &.bottom {
      bottom: -394px;
      right: -271px;
    }
  }
  .the-burger {
    display: none;
    @media screen and (max-width: 1100px) {
      display: block;
    }
  }
}
</style>