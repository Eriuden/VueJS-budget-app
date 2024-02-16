<template>
    <h3>Ajouter une transaction</h3>
    <form id="form" @submit.prevent="onSubmit">
        <div class="form-control">
            <label for="text">Text</label>
            <input type="text" id="text" v-model="text"
             placeholder="Entrez une description"/>
        </div>

        <div class="form-control">
            <label for="amount">
                Montant <br/>
                (négatif - dépenses, positif - revenus)
            </label>
            <input type="text" id="amount" v-model="amount"
             placeholder="Entrez un montant" />
        </div>
        <button class="btn">Ajouter la transaction</button>
    </form>
</template>

<script setup>
    import { ref } from 'vue';

    const text = ref("")
    const amount = ref("")

    const emit = defineEmits(["transaction enregistrée"])

    const onSubmit = () => {
        if (!text.value || !amount.value) {
            window.alert("Les deux champs doivent être remplis")
            return
        }

        const transactionData = {
            text: text.value,
            amount: parseFloat(amount.value)
        }

        emit("transaction enregistrée", transactionData)

        text.value=""
        amount.value=""
    }
    
</script>