<template>
  <div class="the-burger">
    <Slide right width="550">
      <form-wrapper />
    </Slide>
  </div>
</template>
<script>
import { Slide } from "vue-burger-menu";
import FormWrapper from "./sections/FormWrapper.vue";
export default {
  components: { Slide, FormWrapper },
  name: "TheBurger",
};
</script>
<style lang="scss">
.bm-cross-button {
  left: 15px;
  height: 30px;
  width: 30px;
}
</style>