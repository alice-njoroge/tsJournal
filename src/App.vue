<script setup lang="ts">
import TheHeader from "@/components/TheHeader.vue";
import EntryEditor from "./components/EntryEditor.vue";
import EntryCard from "@/components/EntryCard.vue";
import { User } from "@/Types/user";
import { reactive } from "vue";

const user: User = reactive({
  name: "Alice",
  email: "alice@journal.com"
});
</script>

<template>
  <main class="container m-auto p-10">
    <TheHeader />
    <EntryEditor :user="user" />
    <ul>
      <li>
        <EntryCard :user="user" />
      </li>
    </ul>
  </main>
</template>
