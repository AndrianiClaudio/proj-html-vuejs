<template>
  <main class="main">
      <div
      v-for="(section,index) in sections"
      :key='`section-${index}`'
      class="section-container"
      >
      <section :id = 'section.id'>
          <div
          v-for="(container,index) in section.containers"
          :key='`container-${index}`'
          :class="container.name"
          >
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
            <div class="cards" v-if="container.cards">

              <div
              v-for="(card,index) in container.cards"
              :key='`card-${index}`'
              :class="card.name"
              >
                  <!-- eslint-disable max-len -->
                  <img :src=card.img alt="inAlt" v-if="card.img">

                  <div class="title" v-if="card.title">
                      <font-awesome-icon
                      :icon='card.title.icon.name'
                      v-if="card.title.icon && card.title.icon.pickedBy === 'fa'"
                      />
                      <!-- eslint-disable max-len -->
                      <i
                      :class="card.title.icon.class"
                      v-if="card.title.icon && card.title.icon.pickedBy === 'w3_fa'"></i>
                      <span>{{card.title.text}}</span>
                      <div class="subtitle" v-if="card.subtitle">
                          {{card.subtitle}}
                      </div>
                  </div>
                  <div class="paragraphs" v-if="card.paragraphs">
                      <p
                      v-for="(p,index) in card.paragraphs"
                      :key='`card-parag-${index}`'
                      >
                          {{p}}
                      </p>
                  </div>
                  <button v-if="card.button">{{card.button.value}}</button>
              </div>
            </div>
            <div class="paragraphs" v-if="container.paragraphs">
                <p
                v-for="(p,index) in container.paragraphs"
                :key="`paragraph-${index}`"
                >
                    {{p}}
                </p>
            </div>
            <button v-if="container.button">{{container.button.value}}</button>
          </div>

      </section>
      </div>

      <section id="latest-articles">
          latest Articles
          <!-- view All article -->
      </section>

  </main>
</template>

<script>
// todo: inserire icon fontawesome
/* import the fontawesome core */
import { library } from '@fortawesome/fontawesome-svg-core';
/* import specific icons */
import {
  faGlobe,
  faDollarSign,
  faTint,
  faStethoscope,
  faGraduationCap,
} from '@fortawesome/free-solid-svg-icons';
/* import font awesome icon component */
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';

/* add icons to the library */
library.add(
  faGlobe,
  faDollarSign,
  faTint,
  faStethoscope,
  faGraduationCap,
);

export default {
  name: 'Main',
  components: {
    FontAwesomeIcon,
  },
  computed: {

  },
  methods: {
    getNameFromId(i) {
      return i.split('-').join(' ');
    },
  },
  data() {
    return {
      sections: [
        // every-moment-counts
        {
          id: 'every-moment-counts',
          containers: [
            {
              name: 'container-left',
              title: true,
              paragraphs: [
                'Curabitur non mi et turpis pharetra vulputate. Cras consequat, risus nec commodo vehicula, nisi est laoreet leo, ac convallis nisi nibh id velit. Aliquam mattis metus a nisi pretium.',
                'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Praesent ac nibh vestibulum, laoreet ipsum quis, vestibulum nisi. Curabitur non mi et turpis pharetra vulputate. Ipsum dolor sit amet, consectetur adipiscing elit. Praesent ac nibh vestibulum, laoreet ipsum quis, vestibulum nisi.',
                'Curabitur non mi et turpis pharetra vulputate. Cras consequat, risus nec commodo vehicula, nisi est laoreet leo, ac convallis nisi nibh id velit',
              ],
              button: {
                value: 'our mission',
              },
            },
            {
              name: 'container-right',
              title: false,
              cards: [
                {
                  name: 'counts-info',
                  title: {
                    icon: {
                      pickedBy: 'w3_fa',
                      class: 'fa fa-heart-o',
                    },
                    text: '2032',
                  },
                  subtitle: 'Volunteers worldwide',
                },
                {
                  name: 'counts-info',
                  title: {
                    icon: {
                      pickedBy: 'fa',
                      name: 'globe',
                    },
                    text: '132',
                  },
                  subtitle: 'Active projects',
                },
                {
                  name: 'counts-info',
                  title: {
                    icon: {
                      pickedBy: 'fa',
                      name: 'dollar-sign',
                    },
                    text: '3.8M',
                  },
                  subtitle: 'Donated',
                },
              ],
            },
          ],
        },
        // our-values
        {
          id: 'our-values',
          containers: [
            {
              title: true,
              subtitle: 'Think Big. Act Bigger.',
              name: 'container',
              cards: [
                {
                  name: 'our-values-info',
                  title: {
                    icon: {
                      pickedBy: 'fa',
                      name: 'tint',
                    },
                    text: 'clean water',
                  },
                  paragraphs: [
                    'Nullam convallis, orci in congue aliquet, diam mauris cursus urna, Id maximus lectus magna',
                  ],
                  button: {
                    value: 'Learn more',
                  },
                },
                {
                  name: 'our-values-info',
                  title: {
                    icon: {
                      pickedBy: 'fa',
                      name: 'stethoscope',
                    },
                    text: 'Vaccination',
                  },
                  paragraphs: [
                    'Nullam convallis, orci in congue aliquet, diam mauris cursus urna, Id maximus lectus magna',
                  ],
                  button: {
                    value: 'Learn more',
                  },
                },
                {
                  name: 'our-values-info',
                  title: {
                    icon: {
                      pickedBy: 'fa',
                      name: 'graduation-cap',
                    },
                    text: 'Education',
                  },
                  paragraphs: [
                    'Nullam convallis, orci in congue aliquet, diam mauris cursus urna, Id maximus lectus magna',
                  ],
                  button: {
                    value: 'Learn more',
                  },
                },
                {
                  name: 'our-values-info',
                  title: {
                    // icon: {
                    //   pickedBy: 'fa',
                    //   name: '...',
                    // },
                    text: 'farming',
                  },
                  paragraphs: [
                    'Nullam convallis, orci in congue aliquet, diam mauris cursus urna, Id maximus lectus magna',
                  ],
                  button: {
                    value: 'Learn more',
                  },
                },
              ],
            },
          ],
        },
        // recent-causes
        {
          id: 'recent-causes',
          containers: [
            {
              title: true,
              subtitle: 'We run projects in over 30 countries in 5 continents',
              cards: [
                {
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/avada-charity-fair-trade-featured-200x150.jpg'),
                },
                {
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/avada-charity-shelter-featured-200x150.jpg'),
                },
                {
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/avada-charity-farming-featured-200x150.jpg'),

                },
                {
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/avada-charity-vaccines-featured-200x150.jpg'),
                },
              ],
            },
          ],
        },
        {
          id: 'latest-articles',
          containers: [
            {
              title: 'true',
              name: 'container',
              // title: true,
              subtitle: 'Together we make all the difference',
              cards: [
                {
                  name: 'main-card',
                  title: {
                    text: 'Understanding community complexities',
                    // da impostare nel template...come classe in .scss
                    noUppercase: true,
                    applyColor: true,
                  },
                  subtitle: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Prasent ac nibh vestibulum, laoreet ipsum',
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/photo-1444213007800-cff19e1677ac-600x450.jpg'),
                },
                {
                  name: 'sub-card',
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/photo-1444664597500-035db93e2323-177x142.jpg'),
                  title: {
                    text: 'the human story of uniqueness',
                    // da impostare nel template...come classe in .scss
                    applyColor: true,
                    noUppercase: true,
                  },
                  subtitle: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Prasent ac nibh vestibulum, laoreet ipsum',
                },
                {
                  name: 'sub-card',
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/photo-1447430617419-95715602278e-177x142.jpg'),
                  title: {
                    text: 'Sustainable trade tactics',
                    // da impostare nel template...come classe in .scss
                    applyColor: true,
                    noUppercase: true,
                  },
                  subtitle: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Prasent ac nibh vestibulum, laoreet ipsum',
                },
                {
                  name: 'sub-card',
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/photo-1460230525622-630fe3294cd7-177x142.jpg'),
                  title: {
                    text: 'Farmers making a difference',
                    // da impostare nel template...come classe in .scss
                    applyColor: true,
                    noUppercase: true,
                  },
                  subtitle: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Prasent ac nibh vestibulum, laoreet ipsum',
                },
                {
                  name: 'sub-card',
                  title: {
                    // eslint-disable-next-line global-require
                    img: require('../assets/img/photo-1460600421604-5e138c208b9c-177x142.jpg'),
                    text: 'Meeting remote tribes in Peru',
                    // da impostare nel template...come classe in .scss
                    applyColor: true,
                    noUppercase: true,
                  },
                  subtitle: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Prasent ac nibh vestibulum, laoreet ipsum',
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

.section-container {
    section {
        @include flex();
        .title {
            :not(.no-uppercase) {
                text-transform: uppercase;
            }
        }
        hr {
            color: $GoldenrodColor;
            // distanzia riga tra titolo e paragrafi
            margin: 1rem 0;
            width: 200px;

        }
        .paragraphs {
            p {
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
            text-transform: uppercase;
        }
        &#every-moment-counts {
            .container-left {
                //next...variable
                width:70%;
                padding: 5rem;
            }
            .container-right {
                @include flex($dir:column,$jus:center);
                //next..variable
                width:30%;
                //next..variable
                @include bgSet('../assets/img/home-content-bg-1.jpg');
                .counts-info {
                    @include flex($ali:center,$dir: column);
                    padding: 3rem;
                    color: white;
                    //all-icons
                    svg,i {
                        font-size: 1.5rem;
                    }
                }
            }
        }
        &#our-values {
            color: white;
            @include bgSet('../assets/img/home-content-bg-2.jpg');
            .container {
                @include flex($dir:row,$jus:center);
                flex-wrap: wrap;
                padding: 5rem;
                // margin: 0 auto;
                .title {
                    text-align: center;
                    width:100%;
                    hr {
                        margin-left: auto;
                        margin-right: auto;
                    }
                }
                .cards {
                    @include flex();
                    // padding: 3.5rem;
                    .our-values-info {
                        @include flex($dir:column,$ali:center);
                        text-align: center;
                        padding: 1.5rem;
                        .title{
                            * {
                                width: 100%;
                            }
                            svg {
                                font-size: 3.5rem;
                                color: $GoldenrodColor;
                            }
                        }
                    }
                }
            }
        }
        &#recent-causes {
            @include flex($ali:center,$jus:center);
            text-align: center;
            padding: 5rem;
            hr {
                margin-left: auto;
                margin-right: auto;
            }
            .cards {
                padding: 5rem;
                @include flex($gap:1.5rem);
            }
        }
        &#latest-articles {
          .container {
            @include flex();
            flex-wrap: wrap;
            width: 100%;
            padding: 8rem;
            .title {
              width: 100%;
              hr {
                margin: 1rem auto;
              }
              h2 {
                text-align: center;
              }
              .subtitle.no-uppercase {
                text-align: center;
                display: block;
              }
            }
            .cards {
              display: flex;
              padding: 3.2rem;
              .main-card {
                width: 70%;
              }
              .sub-card {
                display: flex;
                align-items: flex-start;
                // flex-direction: column;
                flex-wrap: wrap;
                width:100%;
                img {
                  // align-self: flex-start;
                  width: 25%;
                }
                .title {
                  display: flex;
                  width: 75%;
                  // align-self: flex-end;
                }
              }
            }
          }
        }
    }}
</style>
