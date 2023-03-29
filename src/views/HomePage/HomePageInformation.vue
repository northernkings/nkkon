<template>
  <FeatureSection title="Event information" :variants="['padded', 'black', 'reverse:lg']">
    <p>Across the weekend participants will have the opportunity to take part in:</p>
    <h3>Friday</h3>
    <ul>
      <li>Kings of War Ambush tournament</li>
      <li>Firefight (750pts) tournament</li>
    </ul>
    <h3>Saturday</h3>
    <ul>
      <li>Kings of War singles (2300pts) tournament</li>
      <li>Firefight (1500pts) tournament</li>
    </ul>
    <h3>Sunday</h3>
    <ul>
      <li>Kings of War doubles tournament</li>
      <li>Deadzone tournament</li>
      <li>Armada tournament</li>
    </ul>

    <VButton href="/files/NKGT-2023_EventPack_v1.0.pdf" :variants="['decorative']">
      <template v-slot:icon>
        <IconDownload />
      </template>
      Download the event pack for full details
    </VButton>

    <!-- <p><strong>Tournament Pack to follow.</strong></p> -->

    <template v-slot:media>
      <img
        src="/images/feature-2023-3--900x600.webp"
        alt="Kings of War game in action"
        width="900"
        height="600"
        loading="lazy"
      />
    </template>
  </FeatureSection>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import FeatureSection from "~/components/FeatureSection";
import VButton from "~/components/VButton";
import IconDownload from "~/assets/images/icon-download.svg?component";

export default defineComponent({
  components: {
    FeatureSection,
    VButton,
    IconDownload,
  },
});
</script>
