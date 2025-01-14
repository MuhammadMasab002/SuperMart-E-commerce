<template>
  <div class="container q-px-sm q-pt-md q-pb-xl">
    <div class="row">
      <div class="col q-pb-lg q-pt-sm q-pl-xs">
        <h4
          class="text-h4 text-color-2 fw-medium no-margin q-py-none"
          style="line-height: 28px"
        >
          {{ headTitle }}
        </h4>
      </div>
    </div>
    <div
      class="row justify-between"
      :class="$q.screen.lt.sm ? 'q-col-gutter-y-lg' : 'q-col-gutter-y-lg'"
    >
      <div
        :class="
          $q.screen.lt.lg ? 'col-xs-12 col-sm-4 col-md-3' : 'suppliers-main'
        "
        v-for="(item, index) in supplierList"
        :key="index"
      >
        <div class="flex items-center">
          <div class="bg-accent overflow-hidden flex" style="height: 40px;">
            <img
              class="vertical-middle"
              width="100%"
              height="auto"
              :src="item.flag"
              style="object-fit: contain"
            />
          </div>
          <div class="text-left q-pa-s q-ml-sm">
            <p class="fs-16 fw-regular text-color-2 no-margin">
              {{ item.country }}
            </p>
            <p class="fs-12 fw-light text-color-5 no-margin">
              {{ item.link }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SuppliersByRegion",
  // props: {},
  // computed: {},
  // watch: {},
  // methods: {},
  data() {
    return {
      headTitle: "Suppliers by region",
      supplierList: [
        {
          id: "1",
          country: "Arabic Emirates",
          flag: "/images/flags/1=AE.png",
          link: "shopname.ae",
        },
        {
          id: "2",
          country: "Australia",
          flag: "/images/flags/2=AU.png",
          link: "shopname.au",
        },
        {
          id: "3",
          country: "United States",
          flag: "/images/flags/3=US.png",
          link: "shopname.us",
        },
        {
          id: "4",
          country: "Russia",
          flag: "/images/flags/4=RU.png",
          link: "shopname.ru",
        },
        {
          id: "5",
          country: "Italy",
          flag: "/images/flags/5=IT.png",
          link: "shopname.it",
        },
        {
          id: "6",
          country: "Denmark",
          flag: "/images/flags/6=DK.png",
          link: "shopname.dk",
        },
        {
          id: "7",
          country: "France",
          flag: "/images/flags/7=FR.png",
          link: "shopname.fr",
        },
        {
          id: "8",
          country: "China",
          flag: "/images/flags/8=CN.png",
          link: "shopname.cn",
        },
        {
          id: "9",
          country: "Germany",
          flag: "/images/flags/9=DE.png",
          link: "shopname.de",
        },
        {
          id: "10",
          country: "United Kingdom",
          flag: "/images/flags/10=GB.png",
          link: "shopname.gb",
        },
      ],
    };
  },
  mounted() {
    //...
  },
  methods: {
    //...
  },
};
//
</script>

<style scoped>
.suppliers-main {
  min-width: 272px;
}
</style>
