<template>
  <EditorialSection title="One ticket gives you access to a whole weekend of Mantic gaming goodness." :variants="['reverse:sm']">
    <p class="u-text-4">
      The Northern Kings invite you to join them up in t'north for a full weekend of dice rolling and social antics.
    </p>
    <p>
      A weekend event, held over two and a half days (24th
      to 26th November 2023) at The Ossett War Memorial Community Centre, Wakefield.
    </p>
    <p>
      <strong>More details to follow, but early registration is now open</strong>. Tickets are
      priced at <strong>&pound;55.00</strong>, include a proper lunch on Saturday and Sunday.
    </p>
    <VButton href="/register" :variants="['lg:lg', 'decorative', 'invert']">Register Now</VButton>
    <!-- <VButton disabled :variants="['lg:lg', 'decorative', 'invert']">Sold Out</VButton> -->
    <template v-slot:media>
      <div class="c-media-collage">
        <div class="c-media-collage__section-1">
          <img
            src="/images/in-game-7--600x800.webp"
            alt="Armada miniatures"
            width="600"
            height="800"
            loading="lazy"
          />
        </div>
        <div class="c-media-collage__section-2">
          <img
            src="/images/in-game-6--800x600.webp"
            alt="Firefight miniatures"
            width="800"
            height="600"
            loading="lazy"
          />
          <img
            src="/images/in-game-1--800x800.webp"
            alt="Players at a Northern Kings event"
            width="800"
            height="800"
            loading="lazy"
          />
        </div>
      </div>
    </template>
  </EditorialSection>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import EditorialSection from "~/components/EditorialSection";
import VButton from "~/components/VButton";

export default defineComponent({
  components: {
    EditorialSection,
    VButton,
  },
});
</script>
