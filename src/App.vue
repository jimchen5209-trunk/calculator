<template>
  <input type="number" v-model="a">
  <select name="operand" v-model="operand">
    <option value="" disabled selected>選擇運算子</option>
    <option v-for="symbol in operandSymbles" :key="symbol" :value="symbol">{{ symbol }}</option>
  </select>
  <input type="number" v-model="b">
  = {{ result }}
</template>
<script setup>
import { ref, computed, reactive } from 'vue'
const operandSymbles = reactive(['+','-','*','/']);
const a = ref('')
const b = ref('')
const operand = ref('')
const result = computed(() => { 
  switch (operand.value){
    case '+':
      return a.value + b.value
    case '-':
      return a.value - b.value
    case '*':
      return a.value * b.value
    case '/':
      return a.value / b.value
    default:
      return ''
  }
 })
</script>
