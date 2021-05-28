<template>
  <div class="content">
    <Multiselect v-model="singleValue" :searchable="true" :options="options" />
    <Multiselect
      v-model="multiValue"
      mode="tags"
      :searchable="true"
      :options="options"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import Multiselect from "@vueform/multiselect";

export default defineComponent({
  name: "App",
  components: {
    Multiselect,
  },
  setup() {
    const singleValue = ref();
    const multiValue = ref();

    const options = [
      { value: "batman", label: "Batman" },
      { value: "robin", label: "Robin" },
      { value: "joker", label: "Joker" },
    ];

    return { singleValue, multiValue, options };
  },
});
</script>

<style src="@vueform/multiselect/themes/default.css"></style>

<style>
.content {
  margin: 5rem;
  max-width: 36rem;
  margin-left: auto;
  margin-right: auto;
}

.content > :not([hidden]) ~ :not([hidden]) {
  margin-top: 10rem;
  margin-bottom: 10rem;
}
</style>
