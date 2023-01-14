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

    <div class="categories">
      <div
        class="check-options bg-gray-300 inset-0 absolute flex flex-col items-center justify-center"
      >
        <multi-check-box v-model:value="categories" :options="options" />
      </div>
    </div>

    <div class="generate">
      <button>
        <p>generate</p>
      </button>
    </div>
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
</style>
