<script setup>
// 1
/* import PlanPicker from '@/components/PlanPicker.vue'
import { ref } from 'vue'
const plans = ref(['The Single', 'The Curious', 'The Addict', 'The Hacker'])
const show = ref(true) */

// 2
/* 
import FancyButton from '@/components/FancyButton.vue';
*/

// 3
/* import GitHubCard from '@/components/GitHubCard.vue' */

// 4
import BaseAlert from '@/components/BaseAlert.vue'
import { ref } from 'vue'

const alerts = ref([
  {
    type: 'primary',
    message: 'Primary Alert',
    icon: 'fa-circle-info'
  },
  {
    type: 'success',
    message: 'Success Alert',
    icon: 'fa-check'
  },
  {
    type: 'warning',
    message: 'Warning Alert',
    icon: 'fa-triangle-exclamation'
  },
  {
    type: 'danger',
    message: 'Error Alert',
    icon: 'fa-circle-info'
  }
]);
</script>

<template>
  <!-- 1 -->
  <!-- <div class="content">
    <h1 class="title">Coffee Plans</h1>
    <h2 class="subtitle">
      We travel the world to source the very best single origin coffee for you
    </h2>
    <label>Show Plan Picker<input type="checkbox" v-model="show" /></label>
    <PlanPicker :plans="plans" v-if="show" />
  </div> -->

  <!-- 2 -->
  <!-- <div class="content">
    <FancyButton>
      <template #icon="{hovered}">
        {{ hovered ? '😎' : '😀' }}
      </template>
      Submit
    </FancyButton>
  </div> -->

  <!-- 3 -->
  <!-- <div>
    <GitHubCard username="zouyos" />
  </div> -->

  <!-- 4 -->
  <div class="p-5">
    <BaseAlert v-for="alert in alerts" :key="alert.message" :type="alert.type" @closed="alerts = alerts.filter(a => a.message !== alert.message)">
      <i :class="`fa-solid ${alert.icon} mt-1 mx-2`"></i>
      <template #message> {{alert.message}} </template>
    </BaseAlert>
  </div>
  {{alerts}}
</template>

<style scoped></style>

<!-- #icon = v-slot:icon -->
