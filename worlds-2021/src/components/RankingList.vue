<template>
<div class="wrapper">
    <div v-if="isRankingEmpty" classes="empty-ranking">No item on Ranking</div>
  <div v-else class="teams">
    <div class="team" v-for="team in ranking" :key="team.id">
      <div class="info">
        <h1>{{team.name}}</h1> <h2>({{team.shortname}})</h2>
        <p>{{team.league}}</p> 
      </div>
      <div class="image">
        <img class="teamlogo" :src="'/images/' + team.image">
      </div>
      <div class="likes">
        <h2>{{team.likes}} Likes</h2>
      </div>
      <div class="delete">
        <button class="auto" @click="deleteFromRanking(team)">Delete</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default ({
  name: 'RankingList',
  props: {
    ranking: Array
  },
  computed: {
    isRankingEmpty() {
      return this.$root.$data.votes.length === 0;
    },
  },
  methods: {
    deleteFromRanking(team) {
      this.$root.$data.votes.splice(this.$root.$data.votes.indexOf(team),1);
    }
  }
})
</script>


<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
}

#menu a {
  color: #B84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

.team img {
  border: 2px solid #333;
  height: 200px;
  width: 200px;
  object-fit: contain;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: right;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}
</style>