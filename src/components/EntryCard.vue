<script lang="ts" setup>
import DateDisplay from "./DateDisplay.vue";
import UseEmojis from "@/composables/UseEmojis";
const { findEmoji } = UseEmojis();

const props = defineProps<{
  user: {
    name: String,
    email: String
  }
}>();

</script>
<template>
  <div class="entry-card">
    <div class="entry-card-body">
      <component width="75" :is="findEmoji('happy')"></component>
      <div class="entry-text">Today I enjoyed walking the dog in the park.</div>
    </div>
    <div class="entry-footer">
      <DateDisplay :date="new Date()" class="mr-2" />
      |
      <span class="ml-2">{{props.user.email}}</span>
    </div>
  </div>
</template>
