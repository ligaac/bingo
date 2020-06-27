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

<style scoped>
button {
  height: 10em;
}
</style>