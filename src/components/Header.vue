<template>
  <header class="header">
      <!-- container per logo e navbar-->
    <div class="header-top">
      <!-- eslint-disable max-len -->
      <!-- logo -->
      <img class='logo' src="../assets/img/avada-charity-logo.png" alt="Logo Avada Charity">
      <!-- Lista navbar -->
      <nav>
        <ul>
          <li
          v-for="(item,index) in navbar.items"
          :key="`item-${index}`"
          :class="{'donate-item': navbar.bgSet.includes(item),'active':navbar.active === item}"
          @click = 'activeItem(item)'
          >
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
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  methods: {
    activeItem(item) {
      // button donate si pensa possa avere una funzione a se stante, non attivabile
      if (!this.navbar.bgSet.includes(item)) {
        this.navbar.active = item;
      }
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
  @include bgSet('../assets/img/home-page-slider.jpg');
  height: $headerHeigth;
  width: 100%;
  color: white;
  .header-top {
    @include flex($ali: center,$jus: space-between,$gap:2rem);
    height: $headerTopHeigth;
    width: 90%;
    margin: 0 auto;
    img.logo{
      height: $logoHeigth;
    }
    nav {
      ul {
        @include flex($gap:2.5rem);
        li {
          padding: .75rem 1.25rem;
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
    text-align: center;
    .title {
      font-size: 2.5rem;
      text-transform: uppercase;
    }
    .paragraph {
      &::first-letter {
        text-transform: uppercase;
      }
    }
    .btn-container {
      @include flex($jus:center,$gap:.75rem);
      margin-top:1rem;
      button {
        padding: .6rem 1.25rem;
        text-transform: uppercase;
        font-size: .9rem;
        color: white;
        border: 2px solid white;
        background-color: rgb(0, 0, 0, 0);
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
