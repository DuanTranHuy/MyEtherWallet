<template>
  <div class="link-block wrap">
    <div class="block-icon">
      <img :src="content.icon">
    </div>
    <div>
      <p class="block-title">{{ content.title }}</p>
      <p class="description">{{ content.description }}</p>
      <div
        v-if="content.email"
        class="email">
        <a :href="'mailto:' + content.email"><span>Email us</span><i
          class="fa fa-long-arrow-right"
          aria-hidden="true"/></a>
      </div>
      <div
        v-if="content.social"
        class="social">
        <div
          v-for="social in content.social"
          :key="social.key">
          <a :href="social.link"><img :src="social.icon"></a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    content: {
      type: String,
      default: ''
    }
  },
  data() {
    return {};
  }
};
</script>

<style lang="scss" scoped>
@import 'LinkBlock.scss';
</style>
