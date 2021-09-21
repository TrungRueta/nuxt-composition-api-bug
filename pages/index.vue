<script lang="ts" setup>
import { ref } from "@nuxtjs/composition-api";

const a = ref(true);
</script>

<template>
  <div>
    <Test />

    {{ a }}
  </div>
</template>