<template>
  <div v-if="icon !== 'list' && icon !== 'currency_exchange'">
    <q-item tag="a" target="_blank" :href="link" class="item-link">
      <q-item-section v-if="icon" avatar>
        <q-icon class="item-icon" :name="icon" />
      </q-item-section>

      <q-item-section>
        <q-item-label class="fs-16 fw-light">{{ title }}</q-item-label>
        <q-item-label caption>{{ caption }}</q-item-label>
      </q-item-section>
    </q-item>
  </div>
  <div v-if="icon == 'list'">
    <q-expansion-item
      class="fs-16 fw-light text-blac custom-expansion-header"
      :icon="icon"
      :label="title"
    >
      <q-card class="text-black" v-for="item in subcategories" :key="item">
        <q-card-section class="q-py-sm q-pl-md item-link">
          <p class="no-margin q-pl-lg">
            <q-icon class="item-icon q-mr-sm" size="20px" :name="item.icon" />
            {{ item.name }}
          </p>
        </q-card-section>
      </q-card>
    </q-expansion-item>
  </div>
  <div v-if="icon == 'currency_exchange'">
    <q-expansion-item
      class="fs-16 fw-light text-blac custom-expansion-header"
      :icon="icon"
      :label="title"
    >
      <q-card class="text-black" v-for="item in subcategories" :key="item">
        <q-card-section class="q-py-sm q-pl-md item-link currency-img">
          <div class="flex items-center no-margin q-pl-lg">
            <q-img class="q-mr-sm" width="20px" height="20px" :src="item.flag"/>
            <p class="no-margin q-pl-xs">
              {{ item.name }}
            </p>
          </div>
        </q-card-section>
      </q-card>
    </q-expansion-item>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    caption: String,
    link: String,
    icon: String,
    subcategories: Array,
  },
  // props: {
  //   title: {
  //     type: String,
  //     required: true
  //   },

  //   caption: {
  //     type: String,
  //     default: ''
  //   },

  //   link: {
  //     type: String,
  //     default: '#'
  //   },

  //   icon: {
  //     type: String,
  //     default: ''
  //   }
  // }
};

// const props = defineProps({
//   title: {
//     type: String,
//     required: true
//   },

//   caption: {
//     type: String,
//     default: ''
//   },

//   link: {
//     type: String,
//     default: '#'
//   },

//   icon: {
//     type: String,
//     default: ''
//   }
// })
</script>

<style scoped>
.item-link {
  color: black;
  text-decoration: none;
  transition: color 0.3s ease;

  &:hover {
    background-color: #e5f1ff;
    cursor: pointer;
  }
  .item-icon {
    color: grey;
    transition: color 0.3s ease;
  }
  &:hover {
    &.item-link,
    .item-icon {
      color: #0067ff;
    }
  }
}

.custom-expansion-header {
  background-color: transparent; /* Default background color */
  color: #000;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.custom-expansion-header:hover {
  background-color: #e5f1ff; /* Background color on hover */
  color: #0067ff; /* Optional: Adjust text color on hover */
}

.currency-img .q-img {
  /* mix-blend-mode: luminosity; */
  transition: all 0.3s ease-in-out;
  filter: grayscale(100%);
}
.currency-img:hover .q-img {
  /* mix-blend-mode: luminosity; */
  filter: grayscale(0%);
}
</style>
