<script setup>
const props = defineProps({
  name: {
    type: String,
    default: 'Default Plan',
    required: true,
    validator(value) {
      // return value.startsWith('The') ? true : false
      return value.startsWith('The')
    }
  },
  selected: { type: Boolean, default: false }
})

const emit = defineEmits(['selected'])
// emit sous forme d'objet au lieu de tableau:
// const emit = defineEmits({
//   // si on veut un validator:
//   selected(payload) {
//     return typeof payload === "string"
//   },
//   // sans validator:
//   test: null
// })

function selectPlan() {
  emit('selected', props.name)
}
</script>
<template>
  <div @click="selectPlan" class="plan" :class="{ 'active-plan': selected }">
    <div class="description">
      <span class="title"> {{ props.name }} </span>
    </div>
  </div>
</template>
