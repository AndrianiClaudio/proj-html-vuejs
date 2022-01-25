<template>
  <footer class="footer">
    <div class="sections-container"
    v-for="(section,index) in sections"
    :key="`footer-section-${index}`"
    >
      <Section
      :section = section />
    </div>
  </footer>
</template>

<script>
import Section from './Section.vue';

export default {
  name: 'Footer',
  components: {
    Section,
  },
  data() {
    return {
      sections: [
        {
          id: 'change-a-life-today',
          containers: [
            {
              name: 'container',
              title: true,
              paragraphs: [
                "As long as poverty, injustice & inequality, none of us can truly rest. It doesn't take much to change a life, get in touch today and start making the differnce",
              ],
            },
          ],
        },
      ],
    };
  },
};
</script>

<style>

</style>
