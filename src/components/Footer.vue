<template>
  <footer class="footer">
    <div class="sections-container"
    v-for="(section,index) in sections"
    :key="`footer-section-${index}`"
    >
      <Section
      :section = section />
    </div>
    <div class="footer-copyright">
      <ul>
        <li>
          item
        </li>
        <li>
          item
        </li>
        <li>
          item
        </li>
        <li>
          item
        </li>
      </ul>
      <ul class="icon-list">
        <li>
          <!-- <font-awesome-icon /> -->
          <!-- <font-awesome-icon
          icon='facebook' /> -->
          <!-- <font-awesome-icon icon='facebook-f'/> -->
          <i class="fa fa-facebook"></i>
          <i class="fa fa-instagram"></i>
          <i class="fa fa-twitter"></i>
          <i class="fa fa-youtube"></i>
        </li>
      </ul>
    </div>
  </footer>
</template>

<script>
// import { library } from '@fortawesome/fontawesome-svg-core';
// import {
//   faFacebookF,
// } from '@fortawesome/free-solid-svg-icons';
// import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import Section from './Section.vue';

// library.add(
//   faFacebookF,
// );

export default {
  name: 'Footer',
  components: {
    Section,
    // FontAwesomeIcon,
  },
  data() {
    return {
      sections: [
        {
          id: 'change-a-life-today',
          containers: [
            {
              name: 'container',
              title: true,
              paragraphs: [
                "As long as poverty, injustice & inequality, none of us can truly rest. It doesn't take much to change a life, get in touch today and start making the differnce",
              ],
            },
          ],
        },
        {
          id: 'footer-logo-container',
          containers: [
            {
              name: 'container',
              title: false,
              cards: [
                {
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/avada-charity-mobile-logo-retina.png'),
                },
              ],
            },
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import '../assets/scss/partials/_variables.scss';
@import '../assets/scss/partials/_mixins.scss';

.footer-copyright {
  ul {
    @include flex($jus:center,$gap: 2.5rem)
  }
}
</style>
