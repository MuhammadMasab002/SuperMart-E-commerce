<template>
  <q-page>
    <div class="bg-color-body">
      <Products />
      <NewsLetter />
    </div>
  </q-page>
</template>

<script>
import NewsLetter from "src/components/NewsLetter.vue";
import Products from "../components/Products.vue";
export default {
  name: "ProductList",
  components: {
    Products,
    NewsLetter,
  },
};
//
</script>
