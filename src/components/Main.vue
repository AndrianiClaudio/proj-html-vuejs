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
            <div class="buttons">
                <button>Our Mission</button>
            </div>
          </div>
          <!-- /// left-side -->
          <!-- right-side....bg: home-content-bg-1 -->
          <div class="container-right">
            <!-- volontari -->
            <div class="counts-info">
                <strong>
                    <i class="fa fa-heart-o"></i>
                    2032
                </strong>
                <span>Volunteers worldwide</span>
            </div>
            <div class="counts-info">
                <strong>
                    <font-awesome-icon icon='globe' />
                    132
                </strong>
                <span>Active projects</span>
            </div>
            <div class="counts-info">
                <strong>
                    <font-awesome-icon icon='dollar-sign' />
                    3.8M
                </strong>
                <span>Donated</span>
            </div>
            <!-- <div class="icon-container"> -->
                <!-- <font-awesome-icon icon='heart-o'/> -->
                <!-- <font-awesome-icon icon='heart' class="mini"/> -->
            <!-- </div> -->
            <!-- progetti attivi -->
            <!-- donazioni -->
          </div>
          <!-- /// right-side -->
      </section>
      <section id="values">
          <div class="container">
            <div class="title">
                <h2>our values</h2>
            </div>
            <hr>
            <div class="subtitle">
                <span>
                    Think Big. Act Bigger.
                </span>
            </div>
            <div class="sub-section-container">
                <div id="clean-water">
                    <!--  -->
                    <div class="title">
                        <font-awesome-icon icon='tint'/>
                        <h3>Clean Water</h3>
                    </div>
                    <div class="paragraphs">
                        <p>
                            Nullam convallis, orci in congue aliquet, diam mauris cursus urna, Id maximus lectus magna
                        </p>
                    </div>
                    <div class="buttons">
                        <button>Learn more</button>
                    </div>
                </div>
                <div id="vaccinations">
                    <!--  -->
                    <div class="title">
                        <font-awesome-icon icon='stethoscope'/>
                        <h3>Vaccinations</h3>
                    </div>
                    <div class="paragraphs">
                        <p>
                            Nullam convallis, orci in congue aliquet, diam mauris cursus urna, Id maximus lectus magna
                        </p>
                    </div>
                    <div class="buttons">
                        <button>Learn more</button>
                    </div>
                </div>
                <div id="education">
                    <!--  -->
                    <div class="title">
                        <font-awesome-icon icon='graduation-cap'/>
                        <h3>Education</h3>
                    </div>
                    <div class="paragraphs">
                        <p>
                            Nullam convallis, orci in congue aliquet, diam mauris cursus urna, Id maximus lectus magna
                        </p>
                    </div>
                    <div class="buttons">
                        <button>Learn more</button>
                    </div>
                </div>
                <div id="farming">
                    <!--  -->
                    <div class="title">
                        <!-- todo
                        immagine del grano('wheat') mancante su fontawesome free
                        verra ricercato sostituto.. per ora ha poca importanza
                        -->
                        <h3>Farming</h3>
                    </div>
                    <div class="paragraphs">
                        <p>
                            Nullam convallis, orci in congue aliquet, diam mauris cursus urna, Id maximus lectus magna
                        </p>
                    </div>
                    <div class="buttons">
                        <button>Learn more</button>
                    </div>
                </div>
            </div>
        </div>
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
            background-image: url('../assets/img/home-content-bg-1.jpg');
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
    &#values {
        .container {
            @include flex($dir:column,$ali:center);
            padding: 5rem;
        }
    }
    .sub-section-container {
        @include flex($gap:3.5rem);
        padding: 2.5rem;
    }
}
</style>
