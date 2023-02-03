<script setup>
  import {defineProps} from "vue"
  import {defineEmits} from "vue"

  defineProps(["chose","indexi"]);

  defineEmits(["bDelete","bFaire"]);
</script>

<template>
  <li>
    {{ chose.pourAfficher() }}
    <input type="button" value="delete" @click="$emit('b-delete',indexi)">
    <input type="button" value="faire" @click="$emit('b-faire',indexi)">
  </li>
</template>

<style>
</style>