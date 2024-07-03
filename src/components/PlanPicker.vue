<script setup>
import CoffeePlan from '@/components/CoffeePlan.vue'
import { ref, onMounted, onUnmounted } from 'vue'
defineProps({
  plans: Array
})

const selectedCoffeePlan = ref()

function handleSelectCoffeePlan(name) {
  selectedCoffeePlan.value = name
}

// accéder à des éléments du DOM au lieu d'utiliser des querySelector
const plansWrapper = ref()

// équivalent d'un useEffect en React
onMounted(() => {
  console.log(plansWrapper.value)
})

// équivalent de la fonction de nettoyage du useEffect
const count = ref(0)
const interval = setInterval(() => {
  count.value++
  console.log('hello')
}, 1000)
onUnmounted(() => {
  clearInterval(interval)
})
</script>
<template>
  <div ref="plansWrapper" class="plans">
    {{ count }}
    <CoffeePlan
      v-for="plan in plans"
      :key="plan"
      :name="plan"
      :selected="plan === selectedCoffeePlan"
      @selected="handleSelectCoffeePlan"
    />
  </div>
</template>
