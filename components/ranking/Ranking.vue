<template>
  <v-card class="ranking">
    <v-card-title
      >Ranking (Top 10)
      <nuxt-link to="/rankings" class="ranking__link"
        >View full ranking</nuxt-link
      ></v-card-title
    >
    <v-card-text>
      <ranking-player
        v-for="player in players"
        :key="player.name"
        :player="player"
      ></ranking-player>
    </v-card-text>
  </v-card>
</template>

<script>
import RankingPlayer from "~/components/ranking/RankingPlayer";
import { getRanking } from "~/services/RankingService";
export default {
  name: "Ranking",
  components: {
    RankingPlayer
  },
  data() {
    return {
      players: []
    };
  },
  mounted() {
    this.players = getRanking();
  }
};
</script>

<style lang="scss" scoped>
.ranking {
  width: 100%;

  &__link {
    margin-left: auto;
    text-decoration: none;
    font-size: 0.825rem;

    &:hover {
      text-decoration: underline;
    }
  }
}
</style>
