<script setup>
import { ref } from 'vue'

const props = defineProps({
  type: { type: String, default: 'alert-primary' },
  iconType: { type: String }
})

const emit = defineEmits(['closed'])

const closed = ref(false)

function close() {
  closed.value = true
  emit('closed')
}
</script>

<template>
  <div :class="`alert alert-${props.type} d-flex`" role="alert" v-if="!closed">
    <slot></slot><slot name="message"></slot>
    <button class="ms-auto me-2" @click="close">x</button>
  </div>
</template>
