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
               
import { defineProps } from 'vue';

const props = defineProps({
    transactions: {
        type: Array,
        required: true
    }
})
    
</script>