<template>
  <main class="main">
      <section id="every-moment-counts">
          <!-- left-side -->
          <div class="container-left">
            <!-- titolo -->
            <div class="title">
                <h2>every moment counts</h2>
            </div>
            <hr>
            <div class="paragraphs">
                <!-- eslint-disable max-len -->
                <!-- paragrafo -->
                <p>
                    Curabitur non mi et turpis pharetra vulputate. Cras consequat, risus nec commodo vehicula, nisi est laoreet leo, ac convallis nisi nibh id velit. Aliquam mattis metus a nisi pretium.
                </p>
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Praesent ac nibh vestibulum, laoreet ipsum quis, vestibulum nisi. Curabitur non mi et turpis pharetra vulputate. Ipsum dolor sit amet, consectetur adipiscing elit. Praesent ac nibh vestibulum, laoreet ipsum quis, vestibulum nisi.
                </p>
                <p>
                    Curabitur non mi et turpis pharetra vulputate. Cras consequat, risus nec commodo vehicula, nisi est laoreet leo, ac convallis nisi nibh id velit
                </p>
            </div>
            <!-- bottone -->
            <div>
                <button>Our Mission</button>
            </div>
          </div>
          <!-- /// left-side -->
          <!-- right-side....bg: home-content-bg-1 -->
          <div class="container-right">
            <!-- volontari -->
            <div class="counts-info">
                <strong>iconHearth 2032</strong>
                <span>Volunteers worldwide</span>
            </div>
            <div class="counts-info">
                <strong>iconWorld 132</strong>
                <span>Active projects</span>
            </div>
            <div class="counts-info">
                <strong>iconDollaro 3.8M</strong>
                <span>Donated</span>
            </div>
            <div>
                <font-awesome-icon icon='heart' />
            </div>
            <!-- progetti attivi -->
            <!-- donazioni -->
          </div>
          <!-- /// right-side -->
      </section>
      <section id="values">
          <!-- values -->
      </section>
      <section id="recent-causes">
          recent causes
          <!-- view All causes -->
      </section>
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
import { faHeart } from '@fortawesome/free-solid-svg-icons';
/* import font awesome icon component */
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';

/* add icons to the library */
library.add(faHeart);

export default {
  name: 'Main',
  components: {
    FontAwesomeIcon,
  },
};
</script>

<style lang="scss" scoped>
@import '../assets/scss/partials/_variables.scss';
@import '../assets/scss/partials/_mixins.scss';

section {
    @include flex();
    .title {
        text-transform: uppercase;
    }
    hr {
        color: $GoldenrodColor;
        // distanzia riga tra titolo e paragrafi
        margin: 1rem 0;
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
            hr {
                width: 200px;
            }
        }
        .container-right {
            @include flex($dir:column,$jus:center);
            //next..variable
            width:30%;
            //next..variable
            background-image: url('../assets/img/home-content-bg-1.jpg');
            .counts-info {
                @include flex($ali:center,$dir: column);
                padding: 3rem;
                color: white;
            }
        }
    }
}
</style>
