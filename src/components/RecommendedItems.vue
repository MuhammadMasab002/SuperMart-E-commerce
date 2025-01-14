<template>
  <div class="container q-px-sm q-pt-md q-pb-sm">
    <div class="row">
      <div class="q-pb-lg q-pt-sm q-pl-xs">
        <h4
          class="text-h4 text-color-2 fw-medium no-margin q-py-none"
          style="line-height: 28px"
        >
          {{headTitle}}
        </h4>
      </div>
    </div>
    <div
      class="row justify-center"
      :class="$q.screen.lt.sm ? 'q-gutter-md' : 'q-gutter-lg'"
    >
      <div
        class="bg-white br-6 recommendItems text-center overflow-hidden"
        style="border: 1px solid #dee2e7"
        v-for="(item, index) in recommendList"
        :key="index"
      >
        <div class="q-pa-md img-outer overflow-hidden">
          <!-- :style="$q.screen.lt.md ? { 'height': '250px' } : { 'height': '250px' }" -->
           <div class="overflow-hidden">
             <img
               width="100%"
               height="100%"
               :src="item.image"
               style="object-fit: cover"
             />
           </div>
        </div>
        <div class="text-left q-px-md q-pt-sm q-pb-md">
          <p class="fs-18 fw-regular text-color-2 no-margin">
            {{ item.price }}
          </p>
          <p class="fs-16 fw-light text-color-3 no-margin q-py-xs">
            {{ item.discription }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "RecommendedItems",
  // props: {},
  // computed: {},
  // watch: {},
  // methods: {},
  data() {
    return {
      headTitle: "Recommended items",
      recommendList: [
        {
          id: "1",
          image: "/images/cloth/1.jpg",
          price: "$10.30",
          discription: "T-shirts with multiple colors, for men",
        },
        {
          id: "2",
          image: "/images/cloth/2.jpg",
          price: "$10.30",
          discription: "Brown winter coat for men medium size",
        },
        {
          id: "3",
          image: "/images/cloth/3.jpg",
          price: "$10.30",
          discription: "Casual coat for men with blue color",
        },
        {
          id: "4",
          image: "/images/cloth/4.jpg",
          price: "$10.30",
          discription: "Blue wallet for men leather metarfial",
        },
        {
          id: "5",
          image: "/images/cloth/5.jpg",
          price: "$10.30",
          discription: "Jeans bag for travel for men",
        },

        {
          id: "1",
          image: "/images/others/f1.jpg",
          price: "$10.30",
          discription: "T-shirts with multiple colors, for men",
        },
        {
          id: "2",
          image: "/images/others/k5.webp",
          price: "$10.30",
          discription: "Brown winter coat for men medium size",
        },
        {
          id: "3",
          image: "/images/others/m2.webp",
          price: "$10.30",
          discription: "Casual coat for men with blue color",
        },
        {
          id: "4",
          image: "/images/others/n6.jpg",
          price: "$10.30",
          discription: "Blue wallet for men leather metarfial",
        },
        {
          id: "5",
          image: "/images/others/w5.webp",
          price: "$10.30",
          discription: "Jeans bag for travel for men",
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
.recommendItems {
  text-align: center;
  width: 255px;
  .img-outer img {
    transition: all 0.3s ease-in-out;
  }
  &:hover {
    .img-outer img {
      cursor: pointer;
      transform: scale(1.1);
    }
  }
}
.img-outer {
  height: 250px;
  width: 100%;
  background-color: #fcfbfc;
}
.img-outer img {
  mix-blend-mode: multiply !important;
  object-fit: cover;
}

@media screen and (max-width: 576px) {
  .recommendItems {
    width: 44%;
  }
  .img-outer {
    height: 200px;
  }
}
@media screen and (max-width: 425px) {
  .recommendItems {
    width: 100%;
  }
  .img-outer {
    width: 250px;
    height: 280px;
    margin: 0 auto;
  }
  .img-outer img {
    /* width: 70%; */
    height: auto;
    mix-blend-mode: multiply;
  }
}
</style>
