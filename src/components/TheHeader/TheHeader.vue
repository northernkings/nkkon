<script lang="ts" setup>
import NkkLogo from "~/assets/images/nkk-logo.svg?url";
import NorthernKingsLogo from "~/assets/images/nk-logo-vertical.svg?component";
import VButton from "~/components/VButton";

defineProps({
  compact: Boolean,
});
</script>

<template>
  <header :class="['c-header', compact && 'c-header--compact']">
    <div class="c-header__presents">
      <span class="c-header__presents-label">The</span>
      <a href="https://thenorthernkings.com/">
        <NorthernKingsLogo class="c-header__presents-logo" />
      </a>
      <span class="c-header__presents-label">Present</span>
    </div>
    <div class="c-header__main">
      <template v-if="compact">
        <div class="c-header__logo c-header__logo--compact">
          <a href="/">
            <img :src="NkkLogo as string" class="c-header__logo__image" alt="Northern King Kon" />
          </a>
        </div>
      </template>
      <template v-else>
        <div class="c-header__logo">
          <img :src="NkkLogo as string" class="c-header__logo__image" alt="Northern King Kon" />
        </div>
        <p class="c-header__date">
          Ossett, West Yorkshire. <span>November 24<sup>th</sup> to 26<sup>th</sup> </span>
        </p>
        <!-- <p class="c-header__strapline u-text-uppercase">
          <UkCokLogo class="c-header__cok" />
          Regional Qualifier
        </p> -->
        <!-- <p class="c-header__strapline u-text-uppercase">Sorry, the event has now sold out</p> -->
      </template>
    </div>
    <div class="c-header__book-now">
      <VButton
        class="c-header__book-now__action"
        href="/register"
        :variants="['sm', 'lg:lg', 'decorative', 'ghost']"
      >
        Register Now
      </VButton>
      <!-- <VButton disabled :variants="['sm', 'lg:lg', 'decorative', 'ghost', 'invert']">
        Sold Out
      </VButton> -->
    </div>
  </header>
</template>

<style src="./TheHeader.css"></style>
