<template>
  <div class="container q-px-lg q-pt-sm q-pb-sm">
    <div class="row">
      <div class="col-xs-12">
        <div class="q-py-sm">
          <q-breadcrumbs
            separator="/"
            class="breadcrumbs-items fs-16 fw-regular"
            active-color="grey"
          >
            <q-breadcrumbs-el label="Home" icon="home" />
            <q-breadcrumbs-el label="Products" icon="shopping_bag" />
          </q-breadcrumbs>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-4">
        <div>
          <q-list paddin bordered style="max-width: 328px">
            <q-expansion-item
              v-for="(filter, index) in filterList"
              :key="index"
              :label="filter.label"
              dens
              popup
              header-style="background: #e5f1ff"
              header-class="fs-16 fw-regular"
            >
              <q-card class="filter-item" v-for="item in filter.subcategories" :key="item">
                <q-card-section class="q-py-xs fs-16 fw-light"> {{ item.label }} </q-card-section>
              </q-card>
            </q-expansion-item>
          </q-list>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Products",
  data() {
    return {
      filterList: [
        {
          id: "1",
          label: "Categories",
          subcategories: [
            {
              id: "11",
              label: "Electronics",
            },
            {
              id: "12",
              label: "Fashion",
            },
            {
              id: "13",
              label: "Home & Kitchen",
            },
            {
              id: "14",
              label: "Beauty & Personal Care",
            },
            {
              id: "15",
              label: "Health & Fitness",
            },
            {
              id: "16",
              label: "Baby & Kids",
            },
            {
              id: "17",
              label: "Books & Stationery",
            },
            {
              id: "18",
              label: "Sports & Outdoors",
            },
          ],
        },
      ],
    };
  },
};
//
</script>

<style scoped>
.breadcrumbs-items {
  color: #0067ff;
  .q-breadcrumbs__el {
    &:hover {
      cursor: pointer;
    }
  }
}

.filter-item {
  transition: all 0.3s ease-in-out;
  &:hover {
    color: #0067ff;
    background-color: #e5f1ff;
    cursor: pointer;
  }
}
</style>
