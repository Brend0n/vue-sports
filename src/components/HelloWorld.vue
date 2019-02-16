<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,
      <br>check out the
      <a
        href="https://cli.vuejs.org"
        target="_blank"
        rel="noopener"
      >vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li>
        <a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel"
          target="_blank"
          rel="noopener"
        >babel</a>
      </li>
      <li>
        <a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint"
          target="_blank"
          rel="noopener"
        >eslint</a>
      </li>
    </ul>
    <h3>Essential Link dds</h3>
    <h3>Ecosystem</h3>
    <ul></ul>
  </div>
</template>

<script>
// /* eslint-disable */

import axios from "axios";
export default {
  name: "HelloWorld",
  props: {
    team: Object,
    msg: String
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
        .get("http://api.football-data.org/v2/competitions/PL/teams", {
          headers: { "X-Auth-Token": "eec8bc916c01416b963c97d6d9e27bd8" }
        })
        .then(response => {
          // eslint-disable-next-line
          console.log("mounted");
          // eslint-disable-next-line
          console.log("teams", response.data.teams);
          // let newTeam = [];
          // for (let team of response.data.teams) {
          //   newTeam.push(team.name);
          //   // eslint-disable-next-line
          //   console.log(team.name);
          // }
          this.teams = response.data.teams;
        });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
