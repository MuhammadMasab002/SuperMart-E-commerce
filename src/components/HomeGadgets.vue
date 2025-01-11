<template>
  <div class="container q-px-sm q-pt-md q-pb-sm">
    <div
      class="row justify-center bg-white br-6 overflow-hidden"
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
        <div
          class="q-pa-lg text-color-2"
          :class="$q.screen.lt.md ? '' : 'bg-banner'"
          :style="
            $q.screen.lt.md
              ? {}
              : { 'background-image': 'url(' + title.image + ')' }
          "
        >
          <div>
            <h4
              class="text-h4 text-color-2 fw-medium no-margin q-py-none"
              style="line-height: 28px"
            >
              <!-- Home and <br :class="$q.screen.lt.md ? 'hidden' : 'visible'" />
              outdoor -->
              {{ title.title }}
            </h4>
            <div
              class="q-mt-lg"
              :class="$q.screen.lt.md ? 'hidden' : 'visible'"
            >
              <q-btn
                label="Source more"
                :ripple="false"
                class="br-6 q-py-sm"
                style="
                  background-color: #fff;
                  color: #0d6efd;
                  border: 1px solid #0d6efd;
                "
              />
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
            class="col-xs-6 col-sm-3 col-md-3 col-lg-3 text-center"
            style="border: 1px solid #dee2e7"
            v-for="(item, index) in lists"
            :key="index"
          >
            <div
              class="q-py-xs q-px-md"
              :class="
                $q.screen.lt.lg
                  ? 'reverse column items-center'
                  : 'row justify-around'
              "
            >
              <div class="col-xs-6 col-sm text-left q-pt-md">
                <p class="fs-16 fw-regular text-color-2 no-margin q-py-none">
                  {{ item.title }}
                </p>
                <p class="fs-14 fw-regular text-color-3 q-py-xs">
                  {{ item.discription }}
                </p>
              </div>
              <div class="col-xs-12 col-sm q-pl-m q-pt-lg" style="width: 100px">
                <q-img class="" :src="item.image" />
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-xs-12" :class="$q.screen.lt.md ? 'visible' : 'hidden'">
        <div class="q-my-md q-ml-sm">
          <q-btn
            label="Source more"
            :ripple="false"
            flat
            square
            class="br-6 q-py-sm"
            style="color: #0d6efd"
          >
            <q-icon right size="20px" name="arrow_forward" />
          </q-btn>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DealsAndOffers",
  props: {
    title: Object,
    lists: Array,
  },
  // computed: {},
  // watch: {},
  // methods: {},
  data() {
    return {};
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
.bg-banner {
  width: 100%;
  height: 100%;
  content: "";
  /* background-image: url(/images/banners/Group-1.png); */
  background-repeat: no-repeat;
  background-size: cover;
}
.q-btn:before {
  box-shadow: none;
}
</style>
