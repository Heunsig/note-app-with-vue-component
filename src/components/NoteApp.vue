<script setup>
import { ref } from 'vue';
import NoteForm from './NoteForm.vue';
import NoteList from './NoteList.vue';

defineProps({
  title: {
    type: String,
    default: "Note App(Vue)"
  }
})

const notes = ref([]);
</script>

<template>
  <div class="note-container">
    <h1 class="note-header">{{ title }}</h1>

    <NoteForm @submit="note => {
      notes = [...notes, note];
    }"/>

    <NoteList :notes="notes"/>
  </div>
</template>

<style>
.note-container {
	padding: 1rem .5rem;
	width: clamp(12.5rem, 100%, 25rem);
	margin: 0 auto;
}

.note-header {
	font-size: 1.5rem;
	margin-bottom: 1rem;
}
</style>