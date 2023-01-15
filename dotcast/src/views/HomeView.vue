<template>
  <div class="container">
    <v-row>
      <p>Where do you want to go?</p>
      <!-- <v-card>
        <v-card-text> Where do you want to go? </v-card-text>
      </v-card> -->
    </v-row>

    <v-row>
      <v-select
        label="Select"
        :options="mrtstation"
        placeholder="Source"
      ></v-select>
    </v-row>
    <v-row>
      <v-select
        label="Select"
        :options="[
          'California',
          'Colorado',
          'Florida',
          'Georgia',
          'Texas',
          'Wyoming',
        ]"
        placeholder="Destination"
        variant="solo"
      ></v-select>
    </v-row>

    <!-- <div class="dropdown">
      <v-select
        class="source"
        placeholder="Source"
        solo
        :options="mrtstation"
      ></v-select>

      <v-select
        class="destination"
        placeholder="Destination"
        :options="mrtstation"
      ></v-select> -->
    <!-- </div> -->
    <v-row>
      <v-btn> Generate </v-btn>
    </v-row>
  </div>
</template>

<script>
import vSelect from "vue-select";
import { ref } from "vue";
import { mrtStations } from "./mrtStations";

export default {
  data() {
    return {
      mrtstation: mrtStations,
    };
  },
  setup() {
    let options = ref([]);

    return {
      options,
    };
  },
  components: {
    vSelect,
  },
};
</script>

<style>
.dropdown {
  display: flex;
  justify-content: space-around;
}

.vs_selected {
  visibility: hidden;
}

.vs__actions {
  display: none;
  visibility: hidden;
}

.categories {
  display: flex;
  flex-direction: column;
}

.check-options {
  display: flex;
  flex-direction: column;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 25vh;

  /* max-width: 500px; */
  min-height: 500px;
}

/* .container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 25vh;
} */
</style>
