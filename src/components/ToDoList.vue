<script setup>
  import Chose from "../Chose.js";
  import ToDoListItem from "./ToDoListItem.vue"
  import ToDoForm from "./ToDoForm.vue"
  import {reactive} from "vue"

  const listeC = reactive([new Chose("menage"), new Chose("Vaiselle")]);

  function handlerFaire(index) {
    listeC[index].faire();
  }

  function handlerDelete(index) {
    listeC.splice(index, 1);
  }

  function handlerAdd(l) {
    let p = new Chose(l);
    listeC.push(p);
  }
</script>

<template>
  <h3>Liste des chose à faire</h3>
  <ToDoForm @submit="handlerAdd()"/>
  <ul>
    <ToDoListItem v-for="(chos,index) in listeC" :key="chos.id" :chose="chos" :indexi="index" @b-delete="handlerDelete(index)" @b-faire="handlerFaire(index)"/>
    <!--
    <li v-for="(chos,index) in listeC" :key="chos.id">
      {{ chose.pourAfficher() }}
      <input type="button" value="delete" @click="handlerDelete(index)">
      <input type="button" value="faire" @click="handlerFaire(index)">
    </li>
    -->
  </ul>
</template>