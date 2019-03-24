<template>
    <section class="robots">
        <Robot  v-for="(robot,index) in robotList" :key='index' :robot="robot" :filter="filter"/>
    </section>
</template>

<script>
import Robot from './Robot.vue'
export default {
    components: {
        Robot
    },
     props : ["robotList","filter"]
}
</script>
<style>

</style>
