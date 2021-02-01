<template>
  <ul class="the-footer">
    <li
      class="the-footer__list-item"
      v-for="item in footerLinks"
      :key="item.name"
    >
      <a :href="item.link" class="the-footer__list-item-link">
        <span class="the-footer__list-item-name">{{ item.name }}</span>
      </a>
    </li>
  </ul>
</template>
<script>
export default {
  name: "TheFooter",
  data() {
    return {
      footerLinks: [
        {
          name: "Contact",
          link: "#",
        },
        {
          name: "Privacy",
          link: "#",
        },
        {
          name: "Terms",
          link: "#",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
.the-footer {
  @include flex();
  &__list-item-link {
    color: $button-grey;
    &:hover {
      color: $text-black;
    }
  }

  &__list-item:not(:last-child) {
    margin-right: 25px;
  }
}
</style>