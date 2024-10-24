<script setup>
defineProps({
  count: {
    type: Number,
    required: true,
  }
});
</script>

<template>
  <div class="note-counter">
    <span>{{ count }}</span>개의 메모가 있습니다.
  </div>
</template>

<style>
.note-counter {
	display: flex;
	justify-content:flex-end;
  margin-top: 1rem;
}
</style>