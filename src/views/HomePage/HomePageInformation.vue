<template>
  <FeatureSection title="Event information" :variants="['padded', 'black', 'reverse:lg']">
    <p>Across the weekend participants will have the opportunity to take part in:</p>
    <h3>Friday</h3>
    <ul>
      <li><strong>Kings of War Ambush</strong> - 4:30pm to 9pm, 800pts, 4 games</li>
      <li><strong>Firefight</strong> - 4.30pm to 9pm, 500pts, 4 games</li>
    </ul>
    <h3>Saturday</h3>
    <ul>
      <li><strong>Kings of War singles</strong> - 9am to 6pm, 2300pts, 3 games</li>
      <li><strong>Firefight</strong> - 9am to 6pm, 1500pts, 3 games</li>
      <li><strong>Firefight "Big Tank Bash"</strong> - 7.30pm to 10pm, Participation Game</li>
    </ul>
    <h3>Sunday</h3>
    <ul>
      <li><strong>Kings of War doubles</strong> - 9am to 6pm, 2000pts, 3 games</li>
      <li><strong>Deadzone</strong> - 9am to 6pm, Details tbc</li>
      <li><strong>Armada</strong> - 9am to 6pm, Details tbc</li>
    </ul>

    <!-- <VButton href="/files/NKGT-2023_EventPack_v1.0.pdf" :variants="['decorative']">
      <template v-slot:icon>
        <IconDownload />
      </template>
      Download the event pack for full details
    </VButton> -->

    <!-- <p><strong>Event Pack to follow.</strong></p> -->

    <template v-slot:media>
      <img
        src="/images/feature-3--900x600.webp"
        alt="Firefight army"
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
