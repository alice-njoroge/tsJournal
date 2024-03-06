<script lang="ts" setup>
import EmojiField from "@/components/EmojiField.vue";
import ArrowCircleRight from "@/assets/icons/arrow-circle-right.svg";
import { ref } from "vue";
import type emojis from "@/Types/emojis";

const props = defineProps<{
  user: {
    name: String,
    email: String
  }
}>();

const textInput = ref("");
const emoji = ref<emojis | null>(null);

const selectedEmoji = () => {
  console.log("selected", emoji.value);
};

</script>
<template>
  <form class="entry-form" @submit.prevent>
    <textarea v-model="textInput" :placeholder="`New Journal Entry for ${props?.user?.name}`"></textarea>
    <EmojiField @update:model-value="selectedEmoji" v-model="emoji" />
    <div class="entry-form-footer">
      <span>0 / 280</span>
      <button>Remember
        <ArrowCircleRight width="20" />
      </button>
    </div>
  </form>
</template>
