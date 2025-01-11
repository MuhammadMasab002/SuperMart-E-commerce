<template>
  <div class="container q-px-sm q-pt-md q-pb-sm">
    <div
      class="row br-6 overflow-hidden bg-banner q-py-lg q-px-lg"
      :class="$q.screen.lt.md ? 'justify-center' : 'justify-between'"
    >
      <!-- style="border: 1px solid #dee2e7" -->
      <div class="col-md-4 col-xs-12">
        <!-- :class="$q.screen.lt.md ? '' : 'bg-banner'"
      :style="$q.screen.lt.md ? {} : { 'background-image': 'url(' + title.image + ')' }" -->
        <div
          :class="
            $q.screen.gt.xs
              ? 'q-py-lg q-pr-none'
              : $q.screen.gt.sm
              ? 'q-pa-xl'
              : 'q-pt-sm q-pb-lg'
          "
        >
          <div>
            <h4
              class="fs-32 text-white fw-semibold no-margin q-py-none"
              :class="$q.screen.lt.md ? 'text-center q-pb-sm' : 'text-left'"
              style="line-height: 34px"
            >
              An easy way to send
              <br :class="$q.screen.lt.lg ? 'hidden' : 'visible'" />
              requests to all suppliers
            </h4>
            <div
              class="q-mt-md"
              :class="$q.screen.lt.md ? 'hidden' : 'visible'"
            >
              <p class="fs-16 fw-light no-margin text-white">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
                eiusmod tempor incididunt.
              </p>
            </div>
          </div>
        </div>
      </div>
      <div class="col-xs-12 col-sm-9 col-md-5 self-center">
        <div class="bg-white br-sm q-px-lg q-py-md" style="width: 100%">
          <h4 class="text-h5 text-color-2 fw-medium no-margin">
            Send quote to suppliers
          </h4>
          <q-input
            class="br-sm q-my-md"
            dense
            outlined
            v-model="text"
            label="What item you need?"
            clearable
            style="width: 100%"
          />
          <q-input
            class="br-sm q-my-md bg-white"
            dense
            outlined
            v-model="text"
            standout
            type="textarea"
            placeholder="Type more details"
            clearable
            style="width: 100%"
          />
          <div class="flex q-col-gutter-x-sm">
            <q-input
              class="br-sm bg-white"
              dense
              outlined
              v-model="text"
              standout
              type="number"
              placeholder="Quantity"
              clearable
              :style="$q.screen.lt.md ? { width: '50%' } : { width: '40%' }"
            />
            <!-- style="width: 40%" -->
            <q-select
              class="br-sm bg-white"
              :style="$q.screen.lt.md ? { width: '50%' } : { width: '30%' }"
              dense
              outlined
              v-model="selected"
              :options="['PCs', 'Phones', 'Bags', 'Sets']"
              label="Categories"
              transition-show="jump-up"
              transition-hide="jump-up"
              behavior="default"
            />
          </div>
          <q-btn
            label="Send inquiry"
            :ripple="false"
            class="br-6 q-mt-md q-mb-sm q-py-sm bg-color-gradient text-white"
            style="/* border: 1px solid #0d6efd; */"
          />
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
    return {
      text: "",
      selected: null,
      //...
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
.bg-banner {
  width: 100%;
  height: 100%;
  content: "";
  background-image: url(/images/banners/Form-banner.png);
  background-repeat: no-repeat;
  background-size: cover;
}
.q-btn:before {
  box-shadow: none;
}
</style>
