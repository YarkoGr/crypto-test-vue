<template>
  <div class="main-layout">
    <tabs-wrapper />
    <form-wrapper />
  </div>
</template>
<script>
import FormWrapper from "../components/sections/FormWrapper.vue";
import TabsWrapper from "../components/sections/TabsWrapper.vue";
export default {
  components: { TabsWrapper, FormWrapper },
  name: "MainLayout",
};
</script>
<style lang="scss">
.main-layout {
  @include flex();
  height: 100vh;
  padding: 20px 20px 20px 20px;
  .tabs-wrapper {
    margin-right: 80px;
  }
  > .form-wrapper {
    @media screen and (max-width: 1100px) {
      display: none;
    }
  }
}
</style>