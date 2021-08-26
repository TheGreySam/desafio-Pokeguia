<template>
    <div></div>
</template>

<script>
export default {
    created() {
        fetch("https")
        .then((response) => {
            return response.json();
        })
        .then((datosDelPokemon))
    },
}
</script>

<style scoped>

</style>
