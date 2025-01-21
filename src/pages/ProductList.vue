<template>
  <q-page>
    <div class="bg-color-body">
      <Products />
    </div>
  </q-page>
</template>

<script>
import Products from "../components/Products.vue";
export default {
  name: "ProductList",
  components: {
    Products,
  },
};
//
</script>
