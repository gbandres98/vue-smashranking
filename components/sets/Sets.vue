<template>
  <v-card class="sets">
    <v-card-title
      >Latest sets<nuxt-link to="/sets" class="sets__link"
        >View all sets</nuxt-link
      ></v-card-title
    >
    <v-card-text>
      <set-summary v-for="set in sets" :key="set.id" :set="set"></set-summary>
    </v-card-text>
  </v-card>
</template>

<script>
import SetSummary from "~/components/sets/SetSummary";
import { getSets } from "~/services/SetService";
export default {
  name: "Sets",
  components: {
    SetSummary
  },
  data() {
    return {
      sets: []
    };
  },
  mounted() {
    this.sets = getSets();
  }
};
</script>

<style lang="scss" scoped>
.sets {
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
