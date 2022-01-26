<template>
  <footer class="footer">
    <div class="sections-container"
    v-for="(section,index) in sections"
    :key="`footer-section-${index}`"
    >
      <Section
      :section = section />
    </div>
    <!-- immagine impostata con style -->
    <div id="footer-logo-container"></div>
    <div class="footer-copyright">
      <div class="grey-color">
        <span
        v-for="(txt,index) in copyright.txt"
        :key="`txt-${index}`"
        >
          {{txt}}
          <div class="inline-separator" v-if='index < copyright.txt.length-1'>|</div>
        </span>
      </div>
      <ul class="icon-list">
        <li>
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
import Section from './Section.vue';

export default {
  name: 'Footer',
  components: {
    Section,
  },
  data() {
    return {
      copyright: {
        txt: ['© Copyright 2012 - 2020 AVADA THEME BY THEME FUSION', 'ALL RIGHTS RESERVED', 'POWERED BY WORDPRESS'],
      },
      sections: [
        {
          id: 'change-a-life-today',
          containers: [
            {
              name: 'container',
              title: true,
              paragraphs: [
                "As long as poverty, injustice & inequality persist, none of us can truly rest. It doesn't take much to change a life, get in touch today and start making the difference",
              ],
              button: {
                array: true,
                value: ['Volunteer', 'Donate now'],
              },
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

#footer-logo-container {
  height: 150px;
  @include bgSet('../assets/img/avada-charity-mobile-logo-retina.png',$siz:auto);
}
.footer-copyright {
  text-align: center;
  background-color: rgb($FrenchGrayColor,0.2);
  padding: 4rem;
  .grey-color {
    padding-bottom: 4rem;
    color: $GrayChateauColor;
    font-size: 1.1rem;
    .inline-separator {
      display: inline;
      padding: 2.5rem;
    }
  }
  i {
    margin: auto 1rem;
    padding: 1rem 1.5rem;
    font-size: 2.5rem;
    color: $GoldenrodColor;
    background-color: white;
    border-radius: 50%;
  }
}
</style>
