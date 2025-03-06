<script lang="ts" setup>

    const props = defineProps({
        label: String
    })

</script>

<template>
  <button class="button">
    {{ props.label }}
  </button>
</template>

<style scoped>

.button {
    padding: 0.2em 0.5em;
    color: black;
    background-color: lightgreen;
    font-weight: 700;
    cursor: pointer;
    border: none;
    border-radius: 0.2em;
}


</style>
