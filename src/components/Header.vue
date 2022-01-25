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
          <p class="paragraph">{{jumbo.paragraph}}</p>
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
        // imposta bottoni con sfondo colorato
        bgSet: ['donate'],
        // seleziona item attualmente attivo
        active: 'home',
      },
      jumbo: {
        title: 'Make a difference',
        paragraph: 'as long as proverty, injustice & inequality persist,none of us can truly rest',
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
    height: $headerHeigth;
    width: 100%;
    color: white;
    @include bgSet('../assets/img/home-page-slider.jpg');
    .header-top {
        @include flex($ali: center,$jus: space-between,$gap:2rem);
        width: 90%;
        margin: 0 auto;
        // padding: 1.25rem 4rem;
        // dimensione da settare in _variables.scss
        height: $headerTopHeigth;
        img.logo{
            // dimensione da settare in _variables.scss
            height: 3rem;
        }
        nav {
            ul {
                @include flex($gap:2.5rem );
                li {
                    padding: .5rem 1rem;
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
        @include flex($ali:center,$jus:center,$dir:column,$gap: 1.5rem);
        height: calc(100% - $headerTopHeigth);
        .title {
            text-transform: uppercase;
        }
        .paragraph {
            text-align: center;
            &::first-letter {
                text-transform: uppercase;
            }
        }
        .btn-container {
            @include flex($jus:center,$gap:.5rem);
            margin-top:1rem;
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
