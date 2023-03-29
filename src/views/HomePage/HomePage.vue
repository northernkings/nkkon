<script lang="ts" setup>
import TitleBanner from "~/components/TitleBanner";
import Separator from "~/components/Separator";
import HomePageOverview from "./HomePageOverview.vue";
import HomePageInformation from "./HomePageInformation.vue";
import HomePageAccommodation from "./HomePageAccommodation.vue";
// import HomePageSponsorship from "./HomePageSponsorship.vue";
import HomePageSchedule from "./HomePageSchedule.vue";
import HomePageVenue from "./HomePageVenue.vue";
import HomePageConclusion from "./HomePageConclusion.vue";
// import HomePageHobby from "./HomePageHobby.vue";
import LayoutBase from "~/layouts/LayoutBase";
</script>

<template>
  <LayoutBase>
    <TitleBanner title="A weekend 'konvention' of Mantic games from the Northern Kings." />
    <HomePageOverview />
    <HomePageInformation />
    <!-- <HomePageHobby /> -->
    <HomePageSchedule />
    <Separator />
    <HomePageVenue />
    <HomePageAccommodation />
    <!-- <HomePageSponsorship /> -->
    <Separator />
    <HomePageConclusion />
  </LayoutBase>
</template>

<style src="./HomePage.css"></style>
