<template>
  <footer class="footer">
    <div class="section-container"
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
          <i v-for='(icon,index) in icons'
          :key="`footer-icon-${index}`" :class="icon.join(' ')"></i>

        </li>
      </ul>
      <div class=" absolute">
        <a href="#header">
          <i class="fa fa-angle-up"></i>
        </a>
      </div>
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
      icons: [
        ['fa', 'fa-facebook'],
        ['fa', 'fa-instagram'],
        ['fa', 'fa-twitter'],
        ['fa', 'fa-youtube'],
      ],
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
  position: relative;
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
  .absolute {
    position: absolute;
    bottom:0;
    right: 5rem;
    background-color: $TunaColorMedian;
    color: white;
    a {
      display: block;
      padding: 1rem;
    }

  }
  .icon-list {
    i {
      margin: auto 1rem;
      padding: 1rem 1.5rem;
      font-size: 2.5rem;
      color: $GoldenrodColor;
      background-color: white;
      border-radius: 50%;
      &:hover {
        cursor: pointer;
        background-color: rgba(white, .5);
      }
    }
  }
}
</style>
