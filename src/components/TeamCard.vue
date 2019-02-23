<template >
  <md-card class="card" v-on:click="launchURL">
    <div class="logo">
      <img v-bind:src="team.team.crestUrl">
      <span class="position">{{team.points}} points</span>
    </div>

    <div class="team-name">{{team.team.name}}</div>
    <md-card-content>
      <slot name="content"></slot>
    </md-card-content>

    <md-card-actions md-alignment="left">
      <slot name="footer"></slot>
    </md-card-actions>
  </md-card>
</template>
<script>
export default {
  name: "TeamCard",
  props: {
    dataBackgroundColor: {
      type: String
    },
    team: {
      type: Object
    }
  },
  methods: {
    launchURL: function(team) {
      window.open(team.crestUrl, "windowName");
    }
  }
};
</script>
<style scoped>
.card {
  display: inline-block;
  width: 100%;
  height: 100%;
}
img {
  width: 70px;
  max-height: 80px;
  margin-top: 2px;
}
.position {
  font-size: 18px;
  font-weight: bolder;
  display: block;
  margin-top: 30px;
}
.team-name {
  margin-left: 100px;
  margin-top: 10px;
  justify-content: center;
  font-size: 18px;
  font-weight: bold;
  color: gray;
}
.logo {
  position: absolute;
  top: -20px;
  left: 10px;
  width: 90px;
  height: 100px;
  border: 2px solid gray;
  border-radius: 3px;
}
</style>
