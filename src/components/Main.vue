<template>
  <main class="main">
      <section id="environment-counts">
          <!-- left-side -->
          <div class="container-left">
            <!-- titolo -->
            <h2 class="title">Titolo</h2>
            <!-- eslint-disable max-len -->
            <!-- paragrafo -->
            <p class="paragraph">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam velit soluta ipsam, tempore odio voluptatum recusandae neque corrupti, numquam dolor obcaecati consequuntur possimus minima culpa aut ratione unde totam dolores?</p>
            <p class="paragraph">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam velit soluta ipsam, tempore odio voluptatum recusandae neque corrupti, numquam dolor obcaecati consequuntur possimus minima culpa aut ratione unde totam dolores?</p>
            <p class="paragraph">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam velit soluta ipsam, tempore odio voluptatum recusandae neque corrupti, numquam dolor obcaecati consequuntur possimus minima culpa aut ratione unde totam dolores?</p>
            <!-- bottone -->
            <button>Value</button>
          </div>
          <!-- /// left-side -->
          <!-- right-side....bg: home-content-bg-1 -->
          <div class="container-right">
            <!-- eslint-disable max-len -->
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolore aperiam hic, fugit reprehenderit atque soluta itaque eveniet recusandae voluptas unde exercitationem eos odio repellendus accusantium nisi, natus officiis est velit.
            <!-- volontari -->
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
export default {
  name: 'Main',
};
</script>

<style lang="scss" scoped>
@import '../assets/scss/partials/_variables.scss';
@import '../assets/scss/partials/_mixins.scss';

section {
    @include flex();
    &#environment-counts {
        .container-left {
            width:70%;
            background-color: red;
        }
        .container-right {
            width:30%;
            background-color: blue;
        }
    }
}
</style>
