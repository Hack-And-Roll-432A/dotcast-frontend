<template>
  <div class="mrt-stops">
    <p>Where do you want to go?</p>
    <div class="dropdown">
      <v-select
        class="source"
        placeholder="Source"
        :options="mrtstation"
      ></v-select>

      <v-select
        class="destination"
        placeholder="Destination"
        :options="mrtstation"
      ></v-select>
    </div>

    <div class="categories"></div>
  </div>
</template>

<script>
import vSelect from "vue-select";
export default {
  data() {
    return {
      mrtstation: ["Kent Ridge", "Buona Vista"],
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
</style>
