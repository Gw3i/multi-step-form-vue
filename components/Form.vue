<template>
  <div class="d-flex flex-column align-items-center gap-5 p-3">
    <h1>Multi Step Form</h1>
    <button @click="hello" class="btn-primary">Hello</button>
  </div>
</template>

<script setup>
function hello() {
  alert('Hello')
}
</script>
