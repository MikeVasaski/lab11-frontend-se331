<template>
  <label v-if="label">{{ label }}</label>
  <input
    :value="modelValue"
    :placeholder="label"
    @input="inputHandlers($event)"
    v-bind="$attrs"
    class="field"
  />
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number],
      default: ''
    },
    methods: {
      inputHandlers(event) {
        this.$emit('update: modelValue', event.target.value)
      }
    }
  }
}
</script>
