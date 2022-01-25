<template>
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
            <div v-if="container.sub_cards" class="sub-cards-container">
            <div
            v-for="(subCard,index) in container.sub_cards"
            :key='`sub-card-${index}`'
            :class="subCard.name"
            >
                <!-- eslint-disable max-len -->
                <img :src=subCard.img alt="inAlt" v-if="subCard.img">

                <div class="title" v-if="subCard.title">
                    <span>{{subCard.title.text}}</span>
                    <div class="subtitle" v-if="subCard.subtitle">
                        {{subCard.subtitle}}
                    </div>
                </div>
            </div>

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
// /* import font awesome icon component */
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
// /* add icons to the library */
library.add(
  faGlobe,
  faDollarSign,
  faTint,
  faStethoscope,
  faGraduationCap,
);

export default {
  name: 'Section',
  components: {
    FontAwesomeIcon,
  },
  props: {
    section: Object,
    // FontAwesomeIcon: component,
  },
  methods: {
    getNameFromId(i) {
      return i.split('-').join(' ');
    },
  },
};
</script>

<style lang="scss" scoped>
@import '../assets/scss/partials/_variables.scss';
@import '../assets/scss/partials/_mixins.scss';

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
                @include flex($ali:center,$jus:center,$dir: column);
                text-align: center;
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
        margin: 0 auto;
        width:100%;
        padding: 5rem;
        .title{
            @include flex($dir:column);
            width:100%;
            h2,
            .subtitle {
            text-align: center;
            }
            hr {
            margin: 1rem auto;
            }
        }
        .cards {
            padding: 3rem;
            @include flex($gap: 2.5rem,$jus:center);
            .subtitle {
            text-transform: capitalize;
            text-align: left;
            }
            .main-card {
            @include flex($ali:flex-start,$jus: flex-start,$dir: column);
            width: 600px;
            }
            .sub-cards-container {
                // width: 100%;
                .sub-card{
                padding-bottom: 2rem;
                flex-direction: row;
                display: flex;
                max-width: 600px;
                }
            }
        }
        }
    }
    &#change-a-life-today {
        @include bgSet('../assets/img/home-footer.jpg');
    }
}
</style>
