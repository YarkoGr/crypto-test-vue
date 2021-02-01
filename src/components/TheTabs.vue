<template>
  <div class="the-tabs">
    <a-tabs default-active-key="1" tab-position="bottom">
      <a-tab-pane class="the-tabs__item" key="1" tab="">
        <img :src="graphics.src1" alt="tabs-img" />
        <h2 class="the-tabs__item-title">{{ graphics.name1 }}</h2>
        <span class="the-tabs__item-text">{{ graphics.content1 }}</span>
      </a-tab-pane>
      <a-tab-pane class="the-tabs__item" key="2" tab="">
        <img :src="graphics.src2" alt="tabs-img" />
        <h2 class="the-tabs__item-title">{{ graphics.name2 }}</h2>
        <span class="the-tabs__item-text">{{ graphics.content2 }}</span>
      </a-tab-pane>
      <a-tab-pane class="the-tabs__item" key="3" tab="">
        <img :src="graphics.src3" alt="tabs-img" />
        <h2 class="the-tabs__item-title">{{ graphics.name3 }}</h2>
        <span class="the-tabs__item-text">{{ graphics.content3 }}</span>
      </a-tab-pane>
    </a-tabs>
  </div>
</template>

<script>
export default {
  name: "TheTabs",
  data() {
    return {
      graphics: {
        name1: "Tokenplace",
        src1: require("@/assets/graphics/tokenplace.png"),
        content1: "Multi-exchange Trading Terminal",

        name2: "Fund Platform",
        src2: require("@/assets/graphics/FundPlatform.png"),
        content2: "Hedge funds wealth management",

        name3: "Noviscient",
        src3: require("@/assets/graphics/Noviscient.png"),
        content3: "Management Platform",
      },
    };
  },
};
</script>
<style lang="scss">
.the-tabs {
  &__item {
    text-align: center;
  }
  &__img-wrapper {
    img {
      object-fit: cover;
    }
  }
  &__item-title {
    @include text($h20, 600);
    margin-bottom: 15px;
  }
  &__item-text {
    @include text($h14, 600);
  }
  .ant-tabs-nav-scroll {
    padding-left: 50%;
    transform: translateX(-70px);
  }
  .ant-tabs-nav .ant-tabs-tab {
    padding: 4px;
    top: -6px;
    margin: 0 54px 0 0;
  }
  .ant-tabs-nav {
    max-width: 8px;
    max-height: 8px;
    padding: 0;
  }

  .ant-tabs-nav-container {
    margin-top: 0;
  }
  .ant-tabs-tab {
    width: 8px;
    height: 8px;

    &::after {
      content: "";
      position: absolute;
      height: 8px;
      max-width: 8px;
      border-radius: 4px;
      top: 0;
      left: 0;
      right: 0;
      background-color: $white;
      opacity: 0.4;
      z-index: 1;
    }
  }
  .ant-tabs-ink-bar {
    max-width: 8px;
    height: 8px;
    border-radius: 4px;
    background-color: $white;
    outline: none;
    text-align: center;
  }
}
.ant-tabs-ink-bar-animated {
  transition: transfofr 0s !important;
}
.ant-tabs-bottom .ant-tabs-bottom-bar {
  border-top: none !important;
  margin-top: 0 !important;
  padding-top: 50px;
}
</style>