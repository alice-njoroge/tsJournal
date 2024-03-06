<script lang="ts" setup>
import EmojiField from "@/components/EmojiField.vue";
import ArrowCircleRight from "@/assets/icons/arrow-circle-right.svg";
import { computed, ref } from "vue";
import type emojis from "@/Types/emojis";

const props = defineProps<{
  user: {
    name: String,
    email: String
  }
}>();

const textInput = ref("");
const emoji = ref<emojis | null>(null);
const charCount = computed<number>(() => textInput.value.length);


</script>
<template>
  <form class="entry-form" @submit.prevent>
    <textarea v-model="textInput" :placeholder="`New Journal Entry for ${props?.user?.name}`"></textarea>
    <EmojiField v-model="emoji" />
    <div class="entry-form-footer">
      <span> {{ charCount }} / 280</span>
      <button>Remember
        <ArrowCircleRight width="20" />
      </button>
    </div>
  </form>
</template>
