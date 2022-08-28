<template>
  <div class="card">
    <div class="card-body">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.card {
  background-color: white;
  padding: 2rem;
  border-radius: var(--radius);
}
</style>
