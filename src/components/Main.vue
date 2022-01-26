<template>
  <main class="main">
    <div
    v-for="(section,index) in sections"
    :key='`section-${index}`'
    class="section-container"
    >
      <Section
      :section = section
      />
    </div>
  </main>
</template>

<script>
import Section from './Section.vue';

export default {
  name: 'Main',
  components: {
    Section,
  },
  data() {
    return {
      sections: [
        // ---#every-moment-counts
        {
          id: 'every-moment-counts',
          containers: [
            // container-left
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
            // FINE container-left
            // container-right
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
            // FINE container-right
          ],
        },
        // FINE ---#every-moment-counts
        // ---#our-values
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
                    text: 'Clean water',
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
                    icon: {
                      pickedBy: 'fa',
                      // pickedBy: 'w3_fa',
                      name: 'pagelines',
                      prefix: 'fab',
                    },
                    text: 'Farming',
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
        // FINE ---#our-values
        // --- #recent-causes
        {
          id: 'recent-causes',
          containers: [
            {
              title: true,
              subtitle: 'We run projects in over 30 countries in 5 continents',
              viewAll: {
                txt: 'view all our causes',
              },
              cards: [
                {
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/avada-charity-fair-trade-featured-400x300.jpg'),
                },
                {
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/avada-charity-shelter-featured-400x300.jpg'),
                },
                {
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/avada-charity-farming-featured-400x300.jpg'),

                },
                {
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/avada-charity-vaccines-featured-400x300.jpg'),
                },
              ],
            },
          ],
        },
        // FINE --- #recent-causes
        // ---#latest-articles
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

              ],
              sub_cards: [
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
                  // eslint-disable-next-line global-require
                  img: require('../assets/img/photo-1460600421604-5e138c208b9c-177x142.jpg'),
                  title: {
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
        // FINE ---#latest-articles
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
</style>
