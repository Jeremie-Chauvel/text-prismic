<template>
  <section
    :data-slice-type="slice.slice_type"
    :data-slice-variation="slice.variation"
  >
    <img
      v-if="slice.primary.heroImage.url"
      :src="slice.primary.heroImage.url"
    >
    <div>
      {{ slice.primary.text }}
    </div>
  </section>
</template>

<script setup lang="ts">
import { Content } from "@prismicio/client";

// The array passed to `getSliceComponentProps` is purely optional.
// Consider it as a visual hint for you when templating your slice.
const props = defineProps(
  getSliceComponentProps<Content.HeroSlice>([
    "slice",
    "index",
    "slices",
    "context",
  ])
);
const heroImage = props.slice.primary.heroImage;
const text = props.slice.primary.text;
</script>
