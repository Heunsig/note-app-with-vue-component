<script setup>
import NoteCounter from './NoteCounter.vue';

defineProps({
  notes: {
    type: Array,
    required: true,
  }
});
</script>

<template>
  <section>
    <NoteCounter :count="notes.length"/>

    <ul class="note-list">
      <li 
        class="note-item"
        v-for="note in notes"
      >
        {{ note }}
      </li>
    </ul>
  </section>
</template>

<style>
.note-list {
	list-style: none;
	padding: 0.5rem 0;
	margin: 0;
}

.note-item {
	display: flex;
	align-items: center;
	gap: .5rem;
	padding: .5rem 0;
}

.note-item:not(:last-child) {
	border-bottom: 1px solid #ccc;
}
</style>