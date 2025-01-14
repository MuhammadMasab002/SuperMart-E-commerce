<template>
  <div class="container q-px-sm q-pt-md q-pb-sm">
    <div class="row">
      <div class="q-pb-lg q-pt-sm q-pl-xs">
        <h4
          class="text-h4 text-color-2 fw-medium no-margin q-py-none"
          style="line-height: 28px"
        >
          {{ headTitle }}
        </h4>
      </div>
    </div>
    <div
      class="row justify-cente"
      :class="$q.screen.lt.sm ? 'q-col-gutter-md' : 'q-col-gutter-lg'"
    >
      <div
        class="col-xs-12 col-sm-6 col-md-3 br-6 text-center"
        v-for="(item, index) in services"
        :key="index"
      >
        <div
          class="service-items bg-white overflow-hidden br-6"
          style="border: 1px solid #dee2e7"
        >
          <div class="relative-position">
            <div class="img-outer overflow-hidden">
              <img
                class="vertical-middle"
                width="100%"
                height="100%"
                :src="item.image"
                style="object-fit: cover"
              />
            </div>
            <div
              class="service-icon br-xl flex flex-center shadow-1 bg-color-7 absolute-bottom-right"
            >
              <q-icon size="22px" color="black" :name="item.icon" />
            </div>
          </div>
          <div class="text-left q-pa-md bg-white">
            <p
              class="fs-18 fw-medium text-color-2 no-margin overflow-hidden"
              style="height: 55px; width: 75%"
            >
              {{ item.title }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ExtraServices",
  // props: {},
  // computed: {},
  // watch: {},
  // methods: {},
  data() {
    return {
      headTitle: "Our extra services",
      services: [
        {
          id: "1",
          title: "Source from Industry Hubs",
          icon: "search",
          image: "/images/services/11.png",
        },
        {
          id: "2",
          title: "Customize Your Products",
          icon: "inventory",
          image: "/images/services/22.png",
        },
        {
          id: "3",
          title: "Fast, reliable shipping by ocean or air",
          icon: "send",
          image: "/images/services/33.png",
        },
        {
          id: "4",
          title: "Product monitoring and inspection",
          icon: "security",
          image: "/images/services/44.png",
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
.service-items {
  text-align: center;
  img {
    height: 190px;
    transition: 0.3s ease-in-out;
  }
  &:hover {
    img {
      cursor: pointer;
      transform: scale(1.1);
    }
  }

  @media screen and (max-width: 1023px) {
    img {
      height: 300px;
    }
  }
}

.service-icon {
  width: 55px;
  height: 55px;
  border: 3px solid #fff;
  right: 30px;
  bottom: -27px;
  transition: 0.3s ease-in-out;
  &:hover {
    background-color: #fff;
    border-color: #d1e7ff;
    color: #000;
    cursor: pointer;
  }
}
</style>
