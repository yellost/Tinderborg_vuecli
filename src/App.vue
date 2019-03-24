<template>
  <body>
    <header>
        <div class="title">
            <img class="title__img" src="@/assets/img/tinder.svg" alt="flame">
            <h1 class="title__h1">Meet a 'Borg</h1>
            <span class="title__span">Ça va pécho chez les robots 🤖🍆🍑</span>
        </div>
    </header>
    <Blurb :robotList="robotList.robots" :filter="robotList.filter" :counterMale="robotList.males" :counterFemale="robotList.females" @filterChanged="filterReceived($event)"/>
    <RobotList :robotList="robotList.robots" :filter="robotList.filter"/>
  </body>
</template>

<script>
import axios from 'axios'
import Blurb from './components/Blurb.vue';
import RobotList from './components/Robot-list.vue';
export default {
    data(){
        return {robotList :{
            robots:[],
            filter: "all",
            males:0,
            females:0}
                }
    },
    created(){
        axios.get("https://wt-902485dbb4fca4fccee3a0efcde5b34c-0.sandbox.auth0-extend.com/robots")
        .then(response => {
            this.robotList.robots = response.data;
            this.robotList.males = this.robotList.robots.filter(robot => robot.gender === "Male").length;
            this.robotList.females = this.robotList.robots.filter(robot => robot.gender === "Female").length;
        })
    },
    methods:{
        filterReceived(gender){
            this.robotList.filter = gender
        }
    },
  name: 'app',
  components: { Blurb,
                RobotList
  }
}
</script>

<style lang="scss">
@import 'src/assets/css/style.scss'
</style>
