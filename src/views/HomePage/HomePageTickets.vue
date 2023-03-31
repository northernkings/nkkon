<template>
  <EditorialSection title="A note on tickets…" :variants="['padded']">
    <p class="u-text-4">
      For the first time at a Northern Kings event we're expanding to also hold games on the Friday
      afternoon.
    </p>
    <p>
      We fully understand that due to work, school and other commitments not everyone will be able
      to attend the games on the Friday, but we wanted to maximise the chances to play awesome
      Mantic games for those who are able to make it.
    </p>
    <p>
      If you can't make it, please don't worry. Missing the games on Friday will in no way impact
      your experience of the rest of the weekend. What's more we're not charging any more money for
      the extra half day of games. That means if you can't make it, you're not paying for something
      you can't use. Think of it more like the people who can make are getting an extra freebie!
    </p>
    <p>
      We've made the decision that, to start with, we will not be selling tickets for the individual
      events and the only way to attend is to buy a ticket for the whole weekend. We've done this as
      much as anything to protect ourselves. Hiring out the venue for the whole weekend is costly
      and we need to make sure we can cover our costs.
    </p>
    <p>
      By only selling weekend tickets it helps us make sure that we have enough money to cover the
      entire weekend. If you and friend wanted to band together to share a ticket across the
      weekend, with one of you attending one day and the other the day after that's 100% fine with
      us. But we'll leave that up to you to arrange.
    </p>
    <template v-slot:media>
      <img
        src="/images/illustration-2--900x1142.webp"
        alt="Kings of War illustration"
        width="900"
        height="1142"
        loading="lazy"
        class="u-illustration"
      />
    </template>
  </EditorialSection>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import EditorialSection from "~/components/EditorialSection";

export default defineComponent({
  components: {
    EditorialSection,
  },
});
</script>
