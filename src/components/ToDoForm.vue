<script setup>
  import {defineEmits} from "vue"
  import {ref} from "vue";

  defineEmits(["submitC"]);

  const libelle=ref("")
</script>

<template>
  <form @submit.prevent="$emit('submitC',libelle)"
    <input type="text" v-model="libelle" placeholder="nouvelle chose à faire"/>
    <input type="submit" value="Valider"/>
  </form>
</template>