<script setup>
import { ref } from 'vue';

const emit = defineEmits(['submit']);

const inputValue = ref('');

function addNewNote() {

  if (inputValue.value === '') {
    return;
  }

  emit('submit', inputValue.value);

  inputValue.value = '';
}
</script>

<template>
  <section>
    <form 
      class="note-form"
      @submit.prevent="addNewNote()"
    >
      <input 
        class="form-control note-form__input" 
        type="text" 
        placeholder="Write task..."
        v-model="inputValue"
      >
      <button 
        type="submit"
        class="btn btn-primary note-form__submit"
      >Add</button>
    </form>
  </section>
</template>

<style>
.note-form {
	display: flex;
	gap: 0.5rem;
}

.note-form__input {
	flex: 1;
}
</style>