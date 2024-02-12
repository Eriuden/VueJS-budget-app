<template>
  <Header/>
  <div class="container">
    <Total :total="total"/>
    <RevenusDepenses/>
    <Transactions :transactions="transactions"/>
    <AjoutTransaction/>
  </div>
</template>

<script setup>
  import Header from './components/Header.vue';
  import Total from "./components/Total.vue" 
  import RevenusDepenses from "./components/RevenusDépenses.vue" 
  import Transactions from "./components/Transactions.vue"
  import AjoutTransaction from "./components/AjoutTransaction.vue"

  import {ref, computed} from 'vue';

  const transactions = ref([

  ])

  const total = computed(()=> {
    return transactions.value.reduce((acc,transaction)=> {
      return acc + transaction.amount
    }, 0)
  })
</script>