<script lang="ts" setup>
import { ref } from "@nuxtjs/composition-api";
import { ref as refFromReactivity } from "@vue/reactivity";
import Test from "~/components/Test.vue";

const a = ref(true);
// const b = refFromReactivity('ok');
</script>

<template>
  <div>
    <Test />

    <!-- [a] should be type boolean here
    but in typescript suggest it is Ref<boolean>.
      This bug only happend on typescript type checking, runtime no affected. -->
    <!-- {{ a === true }} -->

    <!-- [b] use reactivy ref, volar understand correct.
    this will not run in runtime because we are using vue 2, but
    correct type checking by volar -->
    <!-- {{ b === 'ok' }} -->
  </div>
</template>
