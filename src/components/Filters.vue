<template>
    <div class="blurb__btn-ctnr">
        <div class="blurb__btn grey" @click="setFilter('all')" data-filter="All">Afficher tout le monde</div>
        <div class="blurb__btn blue" @click="setFilter('Male')" data-filter="Male">Afficher tous les hommes</div>
        <div class="blurb__btn pink" @click="setFilter('Female')" data-filter="Female">Afficher toutes les femmes</div>
    </div>
</template>

<script>
export default {
    methods: {
        log(item) {
            console.log(item);
        },
        setFilter(gender){
            //pour faire remonter la valeur vers le parent
            this.$emit('filterChanged', gender)
        }
    }
}
</script>
<style>

</style>
