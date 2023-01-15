<template>
  <div class="mrt-stops">
    <p class="header">dotCast</p>
    <p class="title">Where do you want to go?</p>
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

    <div class="categories">
      <p class="title">Categories</p>
      <div
        class="check-options bg-gray-300 inset-0 absolute flex flex-col items-center justify-center"
      >
        <multi-check-box v-model:value="categories" :options="options" />
      </div>
    </div>

    <button class="generate"><p>Generate Playlist</p></button>
  </div>
</template>

<script>
import vSelect from "vue-select";
import MultiCheckbox from "../components/multi-checkbox.vue";
import { ref, onMounted } from "vue";

export default {
  data() {
    return {
      mrtstation: ["Kent Ridge", "Buona Vista"],
    };
  },
  setup() {
    let categories = ref([]);
    let options = ref([]);

    const getCategoryOptions = () => {
      options.value = [
        { name: "Sports", id: 1 },
        { name: "Rock", id: 2 },
        { name: "Fantasy", id: 3 },
      ];
    };

    onMounted(() => {
      getCategoryOptions();
    });

    return {
      categories,
      options,
    };
  },
  components: {
    vSelect,
    "multi-check-box": MultiCheckbox,
  },
};
</script>

<style>
.header {
  font-family: "Poppins";
  font-style: normal;
  font-weight: 700;
  font-size: 1.5rem;
  /* identical to box height */

  color: #00ff57;
}

.title {
  font-family: "Poppins";
  font-style: normal;
  font-weight: 700;
  font-size: 1.5rem;
  color: #1e1e1e;
}

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

.vs__search {
  width: 20vw;
  height: 5vh;
  border-radius: 5px;
}

::placeholder {
  font-weight: 500;
  align-content: center;
}

.categories {
  display: flex;
  flex-direction: column;
}

.check-options {
  display: flex;
  flex-direction: column;
}

.generate {
  margin-top: 5vh;
  border-radius: 40px;
  width: 342px;
  height: 68px;
  font-size: 1rem;
  font-weight: 700;
  background: #00ff57;
}
</style>
