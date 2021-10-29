<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('LCK')" href="#" class="pure-menu-link league-link">LCK</a></li>
      <li class="pure-menu-item"><a @click="select('LPL')" href="#" class="pure-menu-link league-link">LPL</a></li>
      <li class="pure-menu-item"><a @click="select('LEC')" href="#" class="pure-menu-link league-link">LEC</a></li>
      <li class="pure-menu-item"><a @click="select('LCS')" href="#" class="pure-menu-link league-link">LCS</a></li>
      <li class="pure-menu-item"><a @click="select('ETC')" href="#" class="pure-menu-link league-link">ETC</a></li>
    </ul>
  </div>
  <TeamList :teams="teams" />
  <hr>
</div>
</template>

<script>
import TeamList from "../components/TeamList.vue"
export default {
  name: 'Browse',
  components: {
    TeamList
  },
  data() {
    return {
      league: '',
    }
  },
  computed: {
    teams() {
        if (this.league === "ETC") {
            return this.$root.$data.teams.filter(team => (!['LCK', 'LPL', 'LEC', 'LCS'].includes(team.league)));
        }
        return this.$root.$data.teams.filter(team => team.league === this.league);
    }
  },
  methods: {
    select(league) {
        this.league = league;
    }
  }
}
</script>

<style>
.pure-menu-link {
  color: rgb(255, 205, 139);
}
.league-link:hover {
  color: darkslategrey;
}
</style>