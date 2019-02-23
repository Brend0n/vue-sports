<template >
  <div class="teams-container">
    <div v-for="team in teams" :key="team.name" class="card-container">
      <div class="position">{{team.position}}-</div>
      <TeamCard data-background-color="orange" v-bind:team="team"></TeamCard>
    </div>
  </div>
</template>

<script>
import TeamCard from "../components/TeamCard";
import axios from "axios";

export default {
  name: "teampage",
  components: {
    TeamCard
  },
  data() {
    return {
      teams: []
    };
  },
  beforeMount() {
    this.getTeam();
  },
  methods: {
    getTeam: function() {
      axios
        .get("http://api.football-data.org/v2/competitions/PL/standings", {
          headers: { "X-Auth-Token": "eec8bc916c01416b963c97d6d9e27bd8" }
        })
        .then(response => {
          // eslint-disable-next-line
          console.log("mounted");
          // eslint-disable-next-line
          console.log("teams", response.data.standings[0].table);
          this.teams = response.data.standings[0].table;
        });
    }
  }
};
</script>

<style scoped>
.teams-container {
  width: 90%;
  margin: auto;
  /* display: inline-block; */
}
.card-container {
  display: flex;
  width: 350px;
  height: 150px;
  margin: 50px auto 30px auto;
}
.position {
  font-size: 27px;
  font-weight: bold;
  margin: 20px 15px;
}
</style>
