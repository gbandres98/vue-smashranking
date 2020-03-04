<template>
  <v-row column>
    <v-col cols="12" md="6">
      <ranking></ranking>
    </v-col>
    <v-col cols="12" md="6">
      <sets></sets>
    </v-col>
  </v-row>
</template>

<script>
import Ranking from "~/components/ranking/Ranking";
import Sets from "~/components/sets/Sets";
export default {
  components: {
    Ranking,
    Sets
  }
};
</script>
