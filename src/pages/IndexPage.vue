<template>
  <q-page>
    <div class="bg-color-body">
      <HeroBanner />
      <DealsAndOffers />
      <HomeGadgets :lists="outdoorList" :title="homeTitle" />
      <HomeGadgets :lists="gadgetList" :title="GadgetTitle" />
      <SupplierForm />
      <RecommendedItems />
    </div>
    <!-- <h1>{{ message }}</h1> -->
  </q-page>
</template>

<script>
import DealsAndOffers from "src/components/DealsAndOffers.vue";
import HeroBanner from "src/components/HeroBanner.vue";
import HomeGadgets from "src/components/HomeGadgets.vue";
import RecommendedItems from "src/components/RecommendedItems.vue";
import SupplierForm from "src/components/SupplierForm.vue";
export default {
  components: {
    HeroBanner,
    DealsAndOffers,
    HomeGadgets,
    SupplierForm,
    RecommendedItems,
  },
  data() {
    return {
      message: "Welcome to Vue.js!",
      homeTitle: {
        title: "Home and outdoor",
        image: "/images/banners/Group-1.png",
      },
      GadgetTitle: {
        title: "Consumer electronics and gadgets",
        image: "/images/banners/Group-2.png",
      },
      outdoorList: [
        {
          id: "1",
          title: "Soft chairs",
          image: "/images/interior/1.jpg",
          discription: "From USD 19",
        },
        {
          id: "2",
          title: "Lamp light",
          image: "/images/interior/2.jpg",
          discription: "From USD 15",
        },
        {
          id: "3",
          title: "Kitchen dishes",
          image: "/images/interior/3.jpg",
          discription: "From USD 22",
        },
        {
          id: "4",
          title: "Smart watches",
          image: "/images/interior/4.png",
          discription: "From USD 11",
        },
        {
          id: "5",
          title: "Kitchen mixer",
          image: "/images/interior/5.jpg",
          discription: "From USD 17",
        },
        {
          id: "6",
          title: "Blenders",
          image: "/images/interior/6.jpg",
          discription: "From USD 19",
        },
        {
          id: "7",
          title: "Home appliance",
          image: "/images/interior/7.jpg",
          discription: "From USD 12",
        },
        {
          id: "8",
          title: "Coffee maker",
          image: "/images/interior/8.jpg",
          discription: "From USD 20",
        },
      ],
      gadgetList: [
        {
          id: "1",
          title: "Smart watches",
          image: "/images/tech/1.jpg",
          discription: "From USD 19",
        },
        {
          id: "2",
          title: "Cameras",
          image: "/images/tech/2.jpg",
          discription: "From USD 15",
        },
        {
          id: "3",
          title: "Headphones",
          image: "/images/tech/3.jpg",
          discription: "From USD 22",
        },
        {
          id: "4",
          title: "Electric kattle",
          image: "/images/tech/4.jpg",
          discription: "From USD 11",
        },
        {
          id: "5",
          title: "Gaming set",
          image: "/images/tech/5.jpg",
          discription: "From USD 17",
        },
        {
          id: "6",
          title: "Laptops & PC",
          image: "/images/tech/6.jpg",
          discription: "From USD 19",
        },
        {
          id: "7",
          title: "Smartphones",
          image: "/images/tech/7.jpg",
          discription: "From USD 12",
        },
        {
          id: "8",
          title: "Smartphones",
          image: "/images/tech/8.jpg",
          discription: "From USD 20",
        },
      ],
    };
  },
};
</script>
