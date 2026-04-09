<script setup>
const props = defineProps({
  type: {
    type: String,
    default: "button",
  },
  color: {
    type: String,
    default: "primary",
  },
  buttonType: {
    type: String,
    default: "button",
  },
  href: {
    type: String,
  },
  size: {
    type: String,
    default: "medium",
  }
});
</script>

<template>
  <button
    v-if="props.type === 'button'"
    :type="props.buttonType"
    class="button"
    :class="`button--${props.color} button--${props.size}`"
  >
    <slot></slot>
  </button>
  <a
    v-else
    :href="props.href"
    class="button"
    :class="`button--${props.color}`"
    >
      <slot></slot>
    </a>
</template>

<style scoped src="./Button.scss" />
