<template>
  <v-app>
    <custom-tshirt></custom-tshirt>
  </v-app>
</template>

<script>
import CustomTshirt from "./components/CustomTshirt";

export default {
  name: 'App',

  components: {
    CustomTshirt,
  },

  data: () => ({
    //q
  }),
};
</script>
<style>
</style>
