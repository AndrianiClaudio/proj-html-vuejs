<template>
  <header class="header">
      <!-- container per logo e navbar-->
      <div class="container">
        <!-- logo -->
        <img class='logo' src="../assets/img/avada-charity-logo.png" alt="Logo Avada Charity">
        <!-- Lista navbar -->
        <nav>
            <ul>
                <li>home</li>
                <li>mission</li>
                <li>causes</li>
                <li>journal</li>
                <li class="donate-item">donate</li>
            </ul>
        </nav>
      </div>

      <!-- container centrato su asse x e y -->
      <div class="jumbo-container">
          <h1 class="title">Make a difference</h1>
          <!-- eslint-disable max-len -->
          <p>As long as proverty&comma; injustice &amp; inequality persist&comma;none of us can truly rest</p>
          <div class="btn-container">
            <button>Our mission</button>
            <button>donate-now</button>
          </div>
      </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
};
</script>

<style lang='scss' scoped>
@import '../assets/scss/partials/_variables.scss';
@import '../assets/scss/partials/_mixins.scss';

header.header {
    height: 750px;
    color: white;
    background-image: url('../assets/img/home-page-slider.jpg');
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    .container {
        @include flex($ali: center,$jus: space-between);
        padding: 1.25rem 4rem;
        img.logo{
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
                }
            }
        }
    }
    .jumbo-container {
        @include flex($ali:center,$jus:center,$dir:column,$gap: 1rem);
        .title {
            text-transform: uppercase;
        }
        .btn-container {
            button {
                text-transform: uppercase;
            }
        }
    }
}
</style>
