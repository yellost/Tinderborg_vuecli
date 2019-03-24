<template>
    <div class="blurb__selection">
        Il y a <span class="blurb__span blue">{{counterMale}} hommes</span> et <span class="blurb__span pink">{{counterFemale}} femmes</span> !
    </div>
</template>

<script>
export default {
    props: ["counterMale","counterFemale"]
}
</script>

<style>

</style>
