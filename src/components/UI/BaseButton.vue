<template>
  <button :class='mode'>
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ['mode']
}
</script>

<style scoped>
button {
  padding: 0.75rem 1.5rem;
  font-family: inherit;
  background-color: #507DBC;
  border: 1px solid #507DBC;
  color: white;
  cursor: pointer;
}

button:hover,
button:active {
  background-color: #04080F;
  border-color: #04080F;
}

.flat {
  background-color: transparent;
  color: #507DBC;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #BBD1EA;
}
</style>