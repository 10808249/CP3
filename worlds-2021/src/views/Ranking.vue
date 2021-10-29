<template>
<div>
  <RankingList :ranking="ranking" />
  <hr>
</div>
</template>

<script>
import RankingList from "../components/RankingList.vue"
export default {
  name: 'Ranking',
  components: {
    RankingList
  },
  data() {
    return {}
  },
  computed: {
    ranking() {
      return this.$root.$data.votes;
    }
  },
  methods: {
  }
}
</script>