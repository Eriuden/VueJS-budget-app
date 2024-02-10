<template>
  <Header/>
  <div class="container">
    <Total/>
    <RevenusDepenses/>
    <Transactions/>
    <AjoutTransaction/>
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import Total from "./components/Total.vue" 
  import RevenusDepenses from "./components/RevenusDépenses.vue" 
  import Transactions from "./components/Transactions.vue"
  import AjoutTransaction from "./components/AjoutTransaction.vue"

  export default {
    components: {
      Header,
      Total,
      RevenusDepenses,
      Transactions,
      AjoutTransaction
    },
  }
</script>