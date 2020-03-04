<template>
  <div class="player">
    <div class="font-weight-black player__rank">{{ player.rank }}</div>
    <nuxt-link class="player__name" to="/">{{ player.name }}</nuxt-link>
    <i :class="`flag-icon flag-icon-${player.country}`" />
    <div class="player__elo">{{ player.elo }} MMR</div>
  </div>
</template>

<script>
export default {
  name: "RankingPlayer",
  props: {
    player: {
      type: Object,
      required: true
    }
  }
};
</script>

<style lang="scss" scoped>
.player {
  display: flex;
  justify-content: space-between;
  padding: 15px 20px;
  background-color: #f0f1f2;
  border: solid 0.5px #e0e0e0;
  margin-top: -1px;

  &__rank {
    font-size: 1.125rem;
  }

  &__name {
    margin-right: auto;
    margin-left: 10px;
    text-decoration: none;
    transition: 0.2s;
    font-weight: 400;
    font-size: 1rem;
    color: #057e8c;

    &:hover {
      color: #08bfd5;
    }
  }

  &__elo {
    color: black;
  }
}

.flag-icon {
  width: 50px;
}
</style>
