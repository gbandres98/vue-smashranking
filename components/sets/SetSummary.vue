<template>
  <div class="set__container">
    <div class="set">
      <div>
        <i :class="`flag-icon flag-icon-${player1.country}`" />
        <nuxt-link class="set__player-name" to="/">{{ set.player1 }}</nuxt-link>
        ({{ player1.elo }})
      </div>
      <span :class="getScore1Class">{{ set.score1 }}</span>
      VS
      <span :class="getScore2Class">{{ set.score2 }}</span>
      <div>
        <i :class="`flag-icon flag-icon-${player2.country}`" />
        <nuxt-link class="set__player-name" to="/">{{ set.player2 }}</nuxt-link>
        ({{ player2.elo }})
      </div>
    </div>
    <div class="set__date">
      {{ getDate }}
    </div>
  </div>
</template>

<script>
import { getPlayer } from "~/services/PlayerService";
export default {
  name: "SetSummary",
  props: {
    set: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      player1: {},
      player2: {}
    };
  },
  computed: {
    getScore1Class() {
      let className = "set__score";
      if (this.set.score1 > this.set.score2) className += " set__score--winner";
      return className;
    },
    getScore2Class() {
      let className = "set__score";
      if (this.set.score2 > this.set.score1) className += " set__score--winner";
      return className;
    },
    getDate() {
      return this.set.date.toDateString();
    }
  },
  mounted() {
    this.player1 = getPlayer(this.set.player1);
    this.player2 = getPlayer(this.set.player2);
  }
};
</script>

<style lang="scss" scoped>
.set {
  display: flex;
  justify-content: space-between;
  padding: 15px 20px 0 20px;

  &__container {
    background-color: #f0f1f2;
    border: solid 0.5px #e0e0e0;
    margin-top: -1px;
  }

  &__player-name {
    text-decoration: none;
    transition: 0.2s;
    font-weight: 400;
    font-size: 1rem;
    color: #057e8c;

    &:hover {
      color: #08bfd5;
    }
  }

  &__score {
    margin: auto;
    font-size: 1.125rem;

    &--winner {
      font-weight: 600;
    }
  }

  &__date {
    padding: 0 0 10px 20px;
    font-size: 0.725rem;
  }
}

.flag-icon {
  width: 50px;
}
</style>
