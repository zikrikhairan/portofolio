<template>
  <footer class="footer">
    <div>&copy; 2019 Zikri Khairan</div>
    <Social :items="groupedPosts['personal-information'].meta.font_awesome"/>
  </footer>
</template>

<script>
import { group } from '../utils'
import Social from './Social'

export default {
  name: 'Footer',
  props: ['posts'],
  components: {
    Social,
  },
  computed: {
    groupedPosts() {
      return group(this.posts)
    },
  },
}
</script>

<style scoped lang="scss">
  @import '@/styles/variables.scss';

  $bg-footer: map-get($colors, dark) !default;

  .footer {
    padding: 5px 20px 0 20px;
    background-color: $bg-footer;
    color: map-get($colors, light);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  /deep/ .social-wrap {
    float: right;

    i {
      font-size: 2.4rem;

      &:hover {
        color: map-get($colors, light);
      }
    }
  }
</style>
