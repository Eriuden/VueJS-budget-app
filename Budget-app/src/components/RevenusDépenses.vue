<template>
    <div class="revenus-dépenses-container">
        <div>
            <h4>Revenus</h4>
            <p id="revenus" class="revenus">+ {{revenus}} €</p>
        </div>
        <div>
            <h4>Dépenses</h4>
            <p id="dépenses" class="dépenses">- {{ dépenses }} €</p>
        </div>
    </div>
</template>

<script setup>
    import { defineProps } from 'vue';

    const props = defineProps({
        revenus: {
            type: Number,
            required: true
        },

        dépenses: {
            type: Number,
            required: true
        }
    })
</script>