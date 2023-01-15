<template>
  <div class="mrt-stops">
    <p class="header">dotCast</p>
    <p class="title">Where do you want to go?</p>
    <div class="dropdown">
      <Dropdown
        v-model="selectedSource"
        :options="mrtstations"
        optionLabel="name"
        :filter="true"
        placeholder="Source"
        :showClear="true"
      >
        <template #value="slotProps">
          <div
            class="source-item source-item-value source"
            v-if="slotProps.value"
          >
            <div>{{ slotProps.value.name }}</div>
          </div>
        </template>
        <template #option="slotProps">
          <div class="source-item">
            <div>{{ slotProps.option.name }}</div>
          </div>
        </template>
      </Dropdown>

      <Dropdown
        v-model="selectedDestination"
        :options="mrtstations"
        optionLabel="name"
        :filter="true"
        placeholder="Destination"
        :showClear="true"
      >
        <template #value="slotProps">
          <div
            class="destination-item destination-item-value destination"
            v-if="slotProps.value"
          >
            <div>{{ slotProps.value.name }}</div>
          </div>
        </template>
        <template #option="slotProps">
          <div class="destination-item">
            <div>{{ slotProps.option.name }}</div>
          </div>
        </template>
      </Dropdown>
    </div>

    <button class="generate"><p>Generate Playlist</p></button>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const selectedSource = ref();
    const selectedDestination = ref();
    const mrtstations = ref([{ name: "Harbourfront", code: "CC29" }]);

    return { selectedSource, selectedDestination, mrtstations };
  },
};
</script>

<style scoped>
.dropdown {
  display: flex;
  justify-content: space-around;
}

.p-dropdown {
  width: 17.5rem;
  height: 5vh;
}

.source {
  border: black 2px;
}

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
