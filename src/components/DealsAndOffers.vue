<template>
  <div class="container q-px-sm q-pt-md q-pb-sm">
    <!-- :class="$q.screen.lt.lg ? 'q-px-sm' : 'q-px-md'" -->
    <div
      class="row justify-center bg-white br-6"
      style="border: 1px solid #dee2e7"
    >
      <div
        class="col-md-3 col-xs-12"
        :style="
          $q.screen.lt.md
            ? 'border-right: none;'
            : 'border-right: 1px solid #dee2e7;'
        "
      >
        <div class="flex justify-between q-gutter-y-md q-py-lg q-pl-md">
          <div class="text-h6 text-left">
            <h4
              class="text-h4 text-color-2 fw-medium no-margin q-py-none"
              style="line-height: 26px"
            >
              Deals and offers
            </h4>
            <h5
              class="text-h5 text-color-3 fw-light no-margin"
              style="line-height: 26px"
            >
              Hygiene equipments
            </h5>
          </div>
          <div class="q-gutter-x-sm"
            :class="$q.screen.lt.md ? 'flex justify-center items-center q-mr-md' : 'flex'"
          >
            <div class="deal-time br-sm bg-color-5 text-center q-py-xs">
              <p class="fs-16 fw-medium text-white no-margin">04</p>
              <p class="fs-14 fw-light text-white no-margin">Days</p>
            </div>
            <div class="deal-time br-sm bg-color-5 text-center q-py-xs">
              <p class="fs-16 fw-medium text-white no-margin">13</p>
              <p class="fs-14 fw-light text-white no-margin">Hour</p>
            </div>
            <div class="deal-time br-sm bg-color-5 text-center q-py-xs">
              <p class="fs-16 fw-medium text-white no-margin">34</p>
              <p class="fs-14 fw-light text-white no-margin">Min</p>
            </div>
            <div class="deal-time br-sm bg-color-5 text-center q-py-xs">
              <p class="fs-16 fw-medium text-white no-margin">56</p>
              <p class="fs-14 fw-light text-white no-margin">Sec</p>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-9 col-xs-12">
        <div
          class="row"
          :style="
            $q.screen.lt.md
              ? 'border-top: 1px solid #dee2e7;;'
              : 'border-top: none'
          "
        >
          <div
            class="col-md col-sm-4 col-xs-6 text-center"
            style="border-right: 1px solid #dee2e7"
            v-for="(item, index) in dealsList"
            :key="index"
          >
            <div class="q-pa-md">
              <q-img width="100%" :src="item.image" />
            </div>
            <p class="fs-16 fw-regular text-color-2 no-margin q-py-sm">
              {{ item.title }}
            </p>
            <p
              class="fs-16 fw-medium bg-color-6 br-lg text-color-4 inline-block q-px-md q-py-xs"
            >
              {{ item.discount }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DealsAndOffers",
  // props: {},
  // computed: {},
  // watch: {},
  // methods: {},
  data() {
    return {
      dealsList: [
        {
          id: "1",
          title: 'Stop Watches',
          image: '/images/tech/8.jpg',
          discount: '-25%'
        },
        {
          id: "2",
          title: 'Laptops',
          image: '/images/tech/7.jpg',
          discount: '-15%'
        },
        {
          id: "3",
          title: 'GoPro cameras',
          image: '/images/tech/6.jpg',
          discount: '-40%'
        },
        {
          id: "4",
          title: 'Headphones',
          image: '/images/tech/5.jpg',
          discount: '-25%'
        },
        {
          id: "5",
          title: 'Canon Cameras',
          image: '/images/tech/4.jpg',
          discount: '-15%'
        }
      ]
    }
  },
  mounted() {
    //...
  },
  methods: {
    //...
  }
}
//
</script>

<style scoped>
.deal-time {
  width: 50px;
  height: auto;
}
</style>
