<template>
  <header class="header">
      <!-- container per logo e navbar-->
      <div class="header-top">
        <!-- logo -->
        <!-- eslint-disable max-len -->
        <img class='logo' src="../assets/img/avada-charity-logo.png" alt="Logo Avada Charity">
        <!-- Lista navbar -->
        <nav>
            <ul>
                <li
                v-for="(item,index) in navbar.items"
                :key="`item-${index}`"
                :class="{'donate-item': navbar.bgSet.includes(item),'active':navbar.active === item}"
                >
                <!-- per possibile uso futuro: attiva item al click -->
                <!-- @click = 'activeItem(item)' -->
                    <a href="#">
                        {{item}}
                    </a>
                </li>
            </ul>
        </nav>
      </div>

      <!-- container centrato su asse x e y -->
      <div class="jumbo">
          <h1 class="title">{{jumbo.title}}</h1>
          <!-- eslint-disable max-len -->
          <p>{{jumbo.paragraph}}</p>
          <div class="btn-container">
              <button
              v-for="(btn,index) in jumbo.buttons"
              :key ='"jumbo-btn-"+index'
              :value="btn.value"
              :class="{'borderSet':btn.borderColor,'colorSet':btn.color}"
              >
                {{btn.value}}
              </button>
            <!-- <button>Our mission</button>
            <button>donate-now</button> -->
          </div>
      </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  methods: {
    activeItem(item) {
      this.navbar.active = item;
    },
  },
  data() {
    return {
      navbar: {
        items: [
          'home',
          'mission',
          'causes',
          'journal',
          'donate',
        ],
        bgSet: ['donate'],
        active: 'home',
      },
      jumbo: {
        title: 'Make a difference',
        paragraph: 'As long as proverty, injustice & inequality persist,none of us can truly rest',
        buttons: [
          {
            value: 'Our mission',
            borderColor: false,
            color: false,
          },
          {
            value: 'donate now',
            borderColor: true,
            color: true,
          },
        ],
      },
    };
  },
};
</script>

<style lang='scss' scoped>
@import '../assets/scss/partials/_variables.scss';
@import '../assets/scss/partials/_mixins.scss';

header.header {
    @include flex($ali:center,$jus:center,$dir:column);
    height: 750px;
    // min-width per gestione ridimensionamento pagina
    min-width: 900px;
    color: white;
    // settaggio immagine di background
    background-image: url('../assets/img/home-page-slider.jpg');
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    .header-top {
        @include flex($ali: center,$jus: space-between,$gap:2rem);
        width: 90%;
        margin: 0 auto;
        // padding: 1.25rem 4rem;
        // dimensione da settare in _variables.scss
        height: 100px;
        img.logo{
            // dimensione da settare in _variables.scss
            height: 3rem;
        }
        nav {
            ul {
                @include flex($gap:3.5rem );
                li {
                    text-transform: uppercase;
                    &.donate-item {
                        background-color: $GoldenrodColor;
                    }
                    &.active {
                        color: $GoldenrodColor;
                    }
                }
            }
        }
    }
    .jumbo {
        @include flex($ali:center,$jus:center,$dir:column,$gap: 1rem);
        height: calc(100% - 100px);
        .title {
            text-transform: uppercase;
        }
        .btn-container {
            @include flex($jus:center,$gap:.5rem);
            button {
                color: white;
                padding: .5rem 1rem;
                text-transform: uppercase;
                border: 2px solid white;
                background-color: rgb(0, 0, 0,0);
                &.borderSet {
                    border-color: $GoldenrodColor;
                }
                &.colorSet {
                    color: $GoldenrodColor;
                }
            }
        }
    }
}
</style>
