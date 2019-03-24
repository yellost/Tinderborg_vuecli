<template>
    <div class="blurb">
        <h2 class="blurb__h2">Faites votre choix</h2>
        <Counter :counterMale="counterMale" :counterFemale="counterFemale"/>
        <div class="blurb__div text">
            Robot ipsum Picoist encephaloform cortropic Filclinic Nippoploid kilolytic zoate. Vesicoity levoparous Egyptococcus stepsepalous stenoales sexuoling ochllyze xeraceae tarsorrhea taxthymia. Cytococcus cheirify gynaecoetic tristomy triboness bathyac conplastic siderogenesis ophioatory egenous. Myary cobaltofuge orphobe pneumonform Angloplex thalassoodont stethometric. Pathoholic newance poikilocline technographer desderma cuprless anthrostat hexgon cyanoicide. Pneumonozyme dendrism exbisect methylphage iridicoable hemoscope anthropomere.
        </div>
        <Filters :filter="filter" @filterChanged="filterReceived($event)"/>
    </div>
</template>

<script>
import Counter from './Counter.vue';
import Filters from './Filters.vue';
export default {
    components: {
        Counter,
        Filters
    },
    props: ["counterMale","counterFemale","robotList","filter"],
    methods:{
        filterReceived(gender){
            this.$emit('filterChanged', gender)
        }
    }

}
</script>

<style>

</style>
