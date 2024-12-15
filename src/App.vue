<template>
  <div class="flex items-center justify-center w-full h-screen bg-gray-100">
    <div
      class="fle flex-col items-center shadow-lg rounded-lg p-8 max-w-[1080px] -mt-80 mx-2"
    >
      <h1 class="text-3xl font-bold text-gray-800 mb-4">
        <span class="text-blue-500 mx-2">{{ DOMAIN }}</span
        >{{ $t("title") }}
      </h1>
      <p class="text-lg text-gray-600">
        {{ $t("description") }}
        <a
          :href="`mailto:${EMAIL}`"
          class="text-blue-500 underline text-lg font-medium mt-2 inline-block"
        >
          {{ EMAIL }}
        </a>
      </p>
      <div class="mt-6 flex flex-warp space-x-2">
        <button
          v-for="language in languages"
          @click="switchLanguage(language.lang)"
          class="px-2 py-1 bg-gray-200 rounded hover:bg-gray-300 duration-300"
        >
          {{ language.name }}
        </button>
        <!-- <button
          @click="switchLanguage('en')"
          class="px-2 py-1 bg-gray-200 rounded"
        >
          English
        </button> -->
      </div>
    </div>
  </div>
</template>

<script setup>
import { useI18n } from "vue-i18n";

const { locale } = useI18n();
const DOMAIN = import.meta.env.VITE_DOMAIN;
const EMAIL = import.meta.env.VITE_EMAIL;

function switchLanguage(lang) {
  locale.value = lang;
}
const languages = [
  {
    lang: "en",
    name: "English",
  },
  {
    lang: "zh",
    name: "中文",
  },
  {
    lang: "ja",
    name: "日本語",
  },
  {
    lang: "ko",
    name: "한국어",
  },
  {
    lang: "es",
    name: "Español",
  },
  {
    lang: "fr",
    name: "Français",
  },
  {
    lang: "de",
    name: "Deutsch",
  },
  {
    lang: "it",
    name: "Italiano",
  },
  {
    lang: "ru",
    name: "Русский",
  },
  {
    lang: "pt",
    name: "Português",
  },
];
</script>

<style scoped></style>
