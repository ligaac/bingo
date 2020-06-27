<template>
  <button type="button" @click="$emit('mark', slug)" :disabled="marked">
    {{ label }}
  </button>
</template>

<script>
export default {
  props: ['label', 'slug', 'marked'],
  methods: {
    mark(slug) {
      this.$emit('mark', slug)
    }
  }
}
</script>

<style scoped lang="postcss">
button {
  @apply py-16 bg-gray-200 rounded transition duration-300 font-bold text-gray-800;
}

button:hover {
  @apply shadow-lg;
}

button:disabled {
  @apply bg-gray-100 text-gray-500 line-through;
}
</style>