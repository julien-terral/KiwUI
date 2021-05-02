<template>
  <button
    type="button"
    :class="[color, textColor, size, isShadowed(), isRounded()]"
    @click="onClick"
    >
    {{ label }}
  </button>
</template>

<script>
export default {
  name: 'KBtn',
  props: {
    /**
     * Size of the width
     * */
    label: {
      type: String,
      required: true,
    },
    color: {
      type: String,
      default: 'bg-green-500',
      required: false,
    },
    textColor: {
      type: String,
      default: 'text-white',
      required: false,
    },
    size: {
      type: String,
      default: 'px-4 py-3 text-md',
      required: false,
    },
    round: {
      type: Boolean,
      default: false,
      required: false,
    },
    shadow: {
      type: Boolean,
      default: false,
      required: false,
    },
  },
  methods: {
    isRounded () {
      if (this.round) { return 'rounded-md' }
    },
    isShadowed () {
      if (this.shadow) { return 'shadow-md' }
    },
    onClick() {
      this.$emit('onClick');
    },
  },
}
</script>
