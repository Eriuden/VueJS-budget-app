<template>
    <h3>Ajouter une transaction</h3>
    <form id="form">
        <div class="form-control">
            <label for="text">Text</label>
            <input type="text" id="text" placeholder="Entrez une description"/>
        </div>

        <div class="form-control">
            <label for="amount">
                Montant <br/>
                (négatif - dépenses, positif - revenus)
            </label>
            <input type="number" id="amount" placeholder="Entrez un montant" />
        </div>
        <button class="btn">Ajouter la transaction</button>
    </form>
</template>