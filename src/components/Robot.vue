<template>
    <div class="robot" :title="robot.first_name+' '+robot.last_name" v-if="filter==robot.gender || filter=='all'">
        <div class="robot__name">
            {{robot.first_name}} <strong>{{robot.last_name}}</strong>
        </div>
        <div class="robot__data" :class="robot.gender">
            <div class="robot__data__type">
                <strong>type</strong> : {{robot.type}}
            </div>
            <img :src="robot.portrait" :alt="robot.first_name+''+robot.last_name">
            <div class="robot__data__language">
                <strong>Langue parlée</strong> : <br>
                {{robot.language}}
            </div>
            <div class="robot__descr">
                {{robot.description}}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props : ["robot","filter"]
}
</script>

<style>

</style>
