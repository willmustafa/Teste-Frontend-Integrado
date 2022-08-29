<template>
  <div class="card">
    <div class="card-body">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardContainer",
};
</script>

<style scoped>
.card {
  background-color: var(--background-darker);
  padding: 2rem;
  border-radius: var(--radius);
}
</style>
