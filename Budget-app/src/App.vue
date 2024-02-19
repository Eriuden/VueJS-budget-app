<template>
  <Header/>
  <div class="container">
    <Total :total="+total"/>
    <RevenusDepenses :revenus="+revenus" :dépenses="+dépenses"/>
    <Transactions :transactions="transactions" 
    @transaction-supprimée="handleTransactionSupprimée"/>
    <AjoutTransaction @transaction-enregistrée="handleTransactionEnregistrée"/>
  </div>
</template>

<script setup>
  import Header from './components/Header.vue';
  import Total from "./components/Total.vue" 
  import RevenusDepenses from "./components/RevenusDépenses.vue" 
  import Transactions from "./components/Transactions.vue"
  import AjoutTransaction from "./components/AjoutTransaction.vue"

  import {ref, computed, onMounted} from 'vue';

  const transactions = ref([

  ])

  onMounted(()=> {
    const savedTransactions = JSON.parse(localStorage.getItem("transactions"))

    if (savedTransactions) {
      transactions.value = savedTransactions
    }
  })

  const total = computed(()=> {
    return transactions.value.reduce((acc,transaction)=> {
      return acc + transaction.amount
    }, 0)
  })

  //Revenus
  const revenus = computed(()=> {
    return transactions.value
      .filter((transaction)=> transaction.amount > 0)
      .reduce((acc, transaction) => {
        return acc + transaction.amount
    }, 0)
    .toFixed(2)
  })
  //Dépenses
  const dépenses = computed(()=> {
    return transactions.value
      .filter((transaction)=> transaction.amount < 0)
      .reduce((acc, transaction) => {
        return acc + transaction.amount
    }, 0)
    .toFixed(2)
  })

  //Ajout transaction

  const handleTransactionEnregistrée = (transactionData) => {
    transactions.value.push({
      id: generateUniqueId(),
      text: transactionData.text,
      amount: transactionData.amount
    })

    saveTransactionsToLocalStorage()
  }

  const generateUniqueId = () => {
    return Math.floor(Math.random() * 1000000)
  }

  const handleTransactionSupprimée = (id) => {
    transactions.value = transactions.value.filter((transaction)=> 
    transaction.id !== id)

    saveTransactionsToLocalStorage()
  }

  const saveTransactionsToLocalStorage = () => {
    localStorage.setItem("transactions", JSON.stringify(transactions.value))
  }

</script>