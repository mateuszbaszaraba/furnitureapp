<template>
  <div class="container">
    <!-- use vue binding to attach the loaded item to ProductDetails props -->
    <product-detail :loadedItem="loadedItem"></product-detail>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

import ProductDetail from "../components/ProductDetail.vue";

export default {
  components: {
    ProductDetail,
  },
  computed: {
    ...mapGetters(["allFurniture"]),
    // get the details here
    loadedItem() {
      return this.allFurniture.find((item) => item.id == this.$route.params.id);
    },
  },
};
</script>

<style></style>
