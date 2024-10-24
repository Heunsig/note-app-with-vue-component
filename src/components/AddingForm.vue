<script setup>

const emit = defineEmits(['submit']);

function addNewNote() {
  const inputEle = document.querySelector('[data-input]');
  const inputValue = inputEle.value;

  if (inputValue === '') {
    return;
  }

  emit('submit', inputValue);

  inputEle.value = '';
}
</script>

<template>
  <section>
    <form 
      class="note-form"
      @submit.prevent="addNewNote"
    >
      <input 
        class="form-control note-form__input" 
        type="text" 
        placeholder="Write task..."
        data-input
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