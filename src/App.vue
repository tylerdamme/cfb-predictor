<template>
  <div id="app">
    <teamItem v-for="team in teams" :team="team" v-bind:key="team.id"/>
  </div>
</template>

<script>
import axios from 'axios';
import TeamItem from './components/TeamItem.vue'

export default {
  name: 'app',
  components: {
    TeamItem
  },

  data() {
    return {
      teams: [],
    }
  },

  mounted() {
    axios.get("https://api.collegefootballdata.com/teams/fbs").then (res => {
      let teamResponse = res.data;
      let bigTen = teamResponse.filter(team => team.conference === "Big Ten");
      this.teams = bigTen;
      console.log(this.teams);
    });
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
