<template >
  <md-card class="card">
    <div class="logo">
      <img v-bind:src="team.crestUrl">
      <span class="founded md-image">{{team.founded}}</span>
    </div>

    <div class="team-name">{{team.name}}</div>
    <md-card-content>
      <slot name="content">terer</slot>
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
.founded {
  font-size: 13px;
  position: absolute;
  bottom: -2px;
  left: 28px;
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
