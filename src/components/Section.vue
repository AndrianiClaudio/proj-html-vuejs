<template>
  <div :id = 'section.id' class="section">
    <div
    v-for="(container,index) in section.containers"
    :key='`container-${index}`'
    :class="container.name"
    >
      <!-- TITOLO SEZIONE -->
      <div class="title" v-if="container.title">
        <h2>{{getNameFromId(section.id)}}</h2>
        <hr>
        <span
        v-if="container.subtitle"
        class="subtitle no-uppercase"
        >
          {{container.subtitle}}
        </span>
      </div>
      <!-- CARDS CONTENT -->
      <div class="cards" v-if="container.cards">
        <div
        v-for="(card,index) in container.cards"
        :key='`card-${index}`'
        :class="card.name"
        >
          <!-- IMMAGINE CARD -->
          <img :src=card.img alt="Errore caricamento immagine" v-if="card.img">
          <!-- CONTAINER TITOLO CARD -->
          <div class="title" v-if="card.title">
            <!-- ICON -->
            <!-- eslint-disable max-len -->
            <font-awesome-icon
            :icon='[card.title.icon.prefix,card.title.icon.name]'
            v-if="card.title.icon && card.title.icon.pickedBy === 'fa'"
            />
            <i
            :class="card.title.icon.class"
            v-if="card.title.icon && card.title.icon.pickedBy === 'w3_fa'"></i>
            <!-- TITOLO CARD -->
            <!-- eslint-disable max-len -->
            <span class="title-txt" v-if="container.name!=='container-right'">{{card.title.text}}</span>
            <!-- permetti la stampa del carattere 3 abbassato rispetto al testo -->
            <div class="inline" v-else
            >
              <div v-for='(txt,index) in card.title.text'
              :key="`txt-${index}`"
              class="inline"
              >
                <span
                :class="{'margin':txt==='3'}"
                >
                  {{txt}}
                </span>
              </div>
            </div>
            <!-- SOTTOTITOLO CARD -->
            <div class="subtitle" v-if="card.subtitle">
              <span>{{card.subtitle}}</span>
            </div>
          </div>
          <!-- CARD PARAGRAPHS -->
          <div class="paragraphs" v-if="card.paragraphs">
            <p
            v-for="(p,index) in card.paragraphs"
            :key='`card-parag-${index}`'
            >
              {{p}}
            </p>
          </div>
          <!-- CARD BUTTON -->
          <button v-if="card.button">{{card.button.value}}</button>
        </div>
        <div v-if="container.sub_cards" class="sub-cards-container">
          <div
          v-for="(subCard,index) in container.sub_cards"
          :key='`sub-card-${index}`'
          :class="subCard.name"
          >
            <!-- IMG SUB-CARD -->
            <img :src=subCard.img alt="inAlt" v-if="subCard.img">
            <!-- TITOLO SUB-CARD -->
            <div class="title" v-if="subCard.title">
                <span class="title-txt">{{subCard.title.text}}</span>
                <div class="subtitle" v-if="subCard.subtitle">
                    {{subCard.subtitle}}
                </div>
            </div>
          </div>
        </div>
      </div>
      <!-- PARAGRAPHS CONTENT -->
      <div class="paragraphs" v-if="container.paragraphs">
        <p
        v-for="(p,index) in container.paragraphs"
        :key="`paragraph-${index}`"
        >
          {{p}}
        </p>
      </div>
      <!-- BUTTON CONTENT-->
      <button v-if="container.button" class="btn">{{container.button.value}}</button>
      <div class="view-all" v-if='container.viewAll'>
        <a href="#">{{container.viewAll.txt}}</a>
      </div>
    </div>
  </div>
</template>

<script>
// /* import the fontawesome core */
import { library } from '@fortawesome/fontawesome-svg-core';
// /* import specific icons */
import {
  faGlobe,
  faDollarSign,
  faTint,
  faStethoscope,
  faGraduationCap,
} from '@fortawesome/free-solid-svg-icons';
import {
  faPagelines,
} from '@fortawesome/free-brands-svg-icons';
// /* import font awesome icon component */
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
// /* add icons to the library */
library.add(
  faGlobe,
  faDollarSign,
  faTint,
  faStethoscope,
  faGraduationCap,
  faPagelines,
);

export default {
  name: 'Section',
  components: {
    FontAwesomeIcon,
  },
  props: {
    section: Object,
  },
  methods: {
    getNameFromId(i) {
      return i.split('-').join(' ');
    },

  },
  // computed: {
  // },
};
</script>

<style lang="scss" scoped>
@import '../assets/scss/partials/_variables.scss';
@import '../assets/scss/partials/_mixins.scss';

.section {

  @include flex();
  .container {
    width: 100%;
    .cards {
        @include flex();
      }
  }
  [class*='container'] {
    padding: 5rem;
  }
  .title {
    text-align: center;
    h2 {
      font-size: 1.75rem;
      text-transform: uppercase;
    }
    hr {
      color: $GoldenrodColor;
      margin: 1.25rem auto;
      border: 2px solid $GoldenrodColor;
      width: 170px;
    }
  }
  .paragraphs {
    p {
      font-size: 1.25rem;
      padding: 1rem 0;
      line-height: 2rem;
    }
  }
  button {
    margin-top: 1rem;
    padding: .5rem 1rem;
    background-color: $GoldenrodColor;
    border:1px solid $GoldenrodColor;
    outline:1px solid $GoldenrodColor;
    color: white;
    // text-transform: uppercase;
    &:hover {
      cursor: pointer;
      background-color: rgba($GoldenrodColor,0.85);
    }
  }
  .cards {
    padding: 5rem;
  }
  // // EVERY MOMENT COUNTS
  &#every-moment-counts {
    .container-left {
      .title {
        text-align: left;
      }
      hr {
        margin-left: 0;
      }
      .paragraphs {
        padding-bottom: .5rem;
      }
      width:$everyCountsContainerWidth;
    }
    .container-right {
        @include flex($ali:center,$jus:center);
        @include bgSet('../assets/img/home-content-bg-1.jpg');
        width:calc(100% - $everyCountsContainerWidth);
        .title {
          @include flex($jus:center);
          flex-wrap: wrap;
          .inline {
            @include flex($jus:center);
            font-size: 2.5rem;
            &::first-child {
              padding-right: 15rem;
            }
          }
          .margin{
          padding-top:.3rem;
          }
          .title-txt {
            font-size: 1.28rem;
          }
          .subtitle {
            width: 100%;
            text-align: center;
            font-size:1.15rem;
          }
        }
        .counts-info {
          text-align: center;
          padding: 1.25rem 0;
          color: white;
          //all-icons
          svg,i,path {
            margin-right: .5rem;
              font-size: 2.5rem;
          }
        }
    }
  }
  // // OUR VALUES
  &#our-values {
    color: white;
    @include bgSet('../assets/img/home-content-bg-2.jpg');
    .container {
      @include flex($dir:row,$jus:center);
      flex-wrap: wrap;
      padding: 5rem;
      .title {
        text-align: center;
        width:100%;
      }
      .cards {
        .our-values-info {
          @include flex($dir:column,$ali:center);
          text-align: center;
          padding: 1.5rem;
          .title{
            @include flex($dir:column,$ali:center,$gap:1rem);
            .title-txt {
              font-size: 1.5rem;
            }
            svg {
              font-size: 5rem;
              color: $GoldenrodColor;
            }
          }
        }
      }
    }
  }
  // RECENT CAUSES
  &#recent-causes {
    @include flex($ali:center,$jus:center);
    padding-top: 5rem;
    .cards {
      @include flex($gap:1.5rem,$jus:center);
      padding-bottom: 2.5rem;
    }
    .view-all {
        height: 100px;
        line-height: 100px;
        background-color: $BurntSiennaColor;
        color: white;
        width: 100%;
    }
  }
  // LATEST ARTICLES
  &#latest-articles {
    *{
        text-align: left;
      }
    .container {
      .title{
        @include flex($dir:column);
        width:100%;
        h2,
        .subtitle {
          text-align: center;
        }
      }
      .cards {
        @include flex($gap: 2.5rem,$jus:center);
        padding: 3.5rem;
        .title-txt {
          color: $GoldenrodColor;
        }
        .subtitle {
          text-align: left;
        }
        .main-card {
          @include flex($dir: column);
          width: 600px;
        }
        .sub-cards-container {
          padding-top:0;
          padding-bottom:0;
          .sub-card{
            @include flex();
            max-width: 600px;
            &:not(:last-child) {
              padding-bottom: 2rem;
            }
          }
        }
      }
    }
  }
  // FOOTER
  &#change-a-life-today {
    @include bgSet('../assets/img/home-footer.jpg');
    color: white;
    p {
      text-align: center;
      font-size: 1.25rem;
    }
  }
}
</style>
