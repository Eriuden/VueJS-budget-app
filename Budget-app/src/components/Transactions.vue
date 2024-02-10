<template>
    <h3>Historique</h3>
        <ul id="liste" class="liste">
            <li v-for="transaction in transactions"
            :key="transaction.id"
            :class="transaction.amount < 0 ? 'moins' : 'plus'">
                {{transaction.text}} <span>{{ transaction.amount }} €</span>
                <button class="delete-button">X</button>
            </li>
        </ul>
</template>

<script setup>
               
const transactions = [
    {id : 1, text: "exemple", amount: 10}
]      
    
</script>