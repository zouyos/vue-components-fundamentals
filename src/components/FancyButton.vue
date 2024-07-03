<script setup>
import { ref } from 'vue';

const hovered = ref(false)
</script>
<template>
    <button class="btn" 
      @mouseenter="hovered = true" 
      @mouseleave="hovered = false"
      >
      <slot name="icon" :hovered="hovered"></slot>
      <slot></slot>
    </button>
</template>
