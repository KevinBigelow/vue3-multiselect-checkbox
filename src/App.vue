<template>
  <div
    class="bg-gray-300 inset-0 absolute flex flex-col items-center justify-center"
  >
    <multi-check-box v-model:value="heroes" :options="options" />
    <div class="mt-4 text-gray-800 font-bold">{{ heroes }}</div>
  </div>
</template>

<script>
import MultiCheckbox from "./components/multi-checkbox.vue";
import { ref, onMounted } from "vue";

export default {
  name: "App",
  setup() {
    let heroes = ref([]);
    let options = ref([]);

    const getMyHeroes = () => {
      heroes.value = [2, 3, 4];
    };

    const getHeroOptions = () => {
      options.value = [
        { name: "Luther", id: 1 },
        { name: "Diego", id: 2 },
        { name: "Allison", id: 3 },
        { name: "Klaus", id: 4 },
        { name: "Five", id: 5 },
        { name: "Ben", id: 6 },
        { name: "Vanya", id: 7 },
      ];
    };

    onMounted(() => {
      getHeroOptions();
      getMyHeroes();
    });

    return {
      heroes,
      options,
    };
  },
  components: {
    "multi-check-box": MultiCheckbox,
  },
};
</script>

<style>
</style>
