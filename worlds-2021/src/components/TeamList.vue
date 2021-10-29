<template>
<div class="wrapper">
  <div class="teams">
    <div class="team" v-for="team in teams" :key="team.id">
      <div class="info">
        <h1>{{team.name}} ({{team.shortname}})</h1>
      </div>
      <div class="image">
        <img :src="'/images/' + team.image">
      </div>
      <div class="like">
        <p>{{team.league}}</p>
        <h2>{{team.seed}}</h2>
        <button class="auto" @click="likeThisTeam(team)">Like</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'TeamList',
  props: {
    teams: Array
  },
  methods: {
    likeThisTeam(team) {
      let isExist = false;
      for (let item of this.$root.$data.votes) {
        if (team.id == item.id) {
          isExist = true;
        }
      }
      if (isExist) {
        team.likes++;
      } else {
        team.likes = 1;
        this.$root.$data.votes.push(team);
      }
      this.$root.$data.votes.sort((a, b) => {return b.likes - a.likes;});
    }
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.teams {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.team {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.team img {
  border: 2px solid #333;
  max-height: 200px;
  max-width: 200px;
  object-fit: contain;
}

.team .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #1da4f2;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.like {
  display: flex;
}

button {
  height: 50px;
  background: rgb(234, 255, 118);
  color: rgb(46, 32, 32);
  border: none;
  border-radius: 5px;
}

.auto {
  margin-left: auto;
}
</style>