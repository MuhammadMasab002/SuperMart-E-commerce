<template>
  <div
    class="container q-py-md"
    :class="$q.screen.lt.sm ? 'q-px-md' : 'q-px-lg'"
  >
    <div class="row">
      <div class="col-xs-12">
        <div class="q-pb-md q-pt-sm">
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
    <div class="row q-pt-sm q-col-gutter-x-md">
      <div
        class="col-xs-12 col-md-3"
        :class="$q.screen.lt.md ? 'hidden' : 'visible'"
      >
        <div>
          <q-separator color="primary" size="2px" />
          <q-list class="bg-white">
            <q-expansion-item
              v-for="(filter, index) in filterList"
              :key="index"
              :label="filter.label"
              dens
              default-opened
              header-style="color: #0067ff"
              header-class="fs-16 fw-regular bg-grey-"
            >
              <q-separator color="grey-4" size="2px" />
              <q-card
                :class="[
                  { 'active-filter-item': item.modelValue },
                  'filter-ite',
                ]"
                :ripple="false"
                v-for="item in filter.subcategories"
                :key="item"
              >
                <q-item
                  class="fs-14 fw-light"
                  tag="label"
                  dense
                  :ripple="false"
                >
                  <!-- v-if="item.modelValue == true" -->
                  <q-item-section
                    v-if="
                      filter.label !== 'Categories' && filter.label !== 'Price'
                    "
                    avatar
                  >
                    <q-checkbox
                      v-model="item.modelValue"
                      :val="item.label.toLowerCase().replace(' ', '')"
                      color="primary"
                    />
                  </q-item-section>
                  <q-item-section
                    v-if="
                      filter.label !== 'Categories' && filter.label == 'Price'
                    "
                    avatar
                    style="width: 100%"
                    class="q-pb-lg q-pt-md"
                  >
                    <q-range
                      class="q-pb-sm"
                      v-model="item.range"
                      :min="0"
                      :max="100"
                      :step="10"
                      :inner-min="0"
                      :inner-max="100"
                      label
                      label-always
                      switch-label-side
                      drag-range
                      track-size="6px"
                      inner-track-color="transparent"
                    />
                  </q-item-section>
                  <q-item-section
                    v-if="
                      filter.label !== 'Categories' && filter.label == 'Rating'
                    "
                    avatar
                    style="width: 100%"
                    class=""
                  >
                    <q-rating
                      v-model="item.ratingModel"
                      size="1.5em"
                      color="primary"
                      readonly
                    />
                  </q-item-section>
                  <q-item-section
                    v-if="filter.label !== 'Price' && filter.label !== 'Rating'"
                  >
                    <q-item-label> {{ item.label }}</q-item-label>
                  </q-item-section>
                </q-item>
              </q-card>
              <!-- <q-separator color="primary" size="2px" /> -->
            </q-expansion-item>
          </q-list>
        </div>
      </div>
      <div class="col-xs-12 col-md-9">
        <div class="row">
          <div class="col-xs-12">
            <div
              class="products-grid flex justify-between items-center q-py-sm bg-white br-6"
              :class="$q.screen.lt.sm ? 'q-px-sm' : 'q-px-md'"
              style="border: 2px solid #dee2e7"
            >
              <div>
                <h5 class="text-h5 fw-regular text-color-2 no-margin">
                  <span :class="$q.screen.lt.sm ? 'hidden' : 'visible'"
                    >Results for</span
                  >
                  <span class="text-italic q-pr-xs">"Electronics": </span>
                  <span class="fs-16 text-primary">21</span>
                </h5>
              </div>
              <div class="flex items-center">
                <div
                  class="bg-white br-6"
                  :class="$q.screen.lt.sm ? 'q-mr-xs' : $q.screen.lt.md ? 'q-mr-sm  visible' : 'hidden'"
                  style="border: 2px solid #dee2e7"
                >
                  <q-btn
                    flat
                    dense
                    color="grey-6"
                    :ripple="false"
                    size="1em"
                    icon="filter_alt"
                  />
                </div>

                <p
                  class="fs-16 fw-regular no-margin q-pr-sm"
                  :class="$q.screen.lt.sm ? 'hidden' : 'visible'"
                >
                  Layout:
                </p>
                <div class="my-custom-toggle br-6 overflow-hidden">
                  <q-btn-toggle
                    v-model="gridModel"
                    spread
                    size="md"
                    dense
                    no-caps
                    unelevated
                    toggle-color="grey-4"
                    toggle-text-color="black"
                    glossy
                    :ripple="false"
                    :options="[
                      { icon: 'grid_view', value: 'grid' },
                      { icon: 'view_list', value: 'list' },
                    ]"
                  />
                </div>
                <!-- <div class="flex flex-center br-6">
                  <div
                    class="bg-whit q-px-sm br-6 text-dark q-py-xs grid-btn"
                    style="border: 2px solid #DEE2E7; border-top-right-radius: 0; border-bottom-right-radius: 0; "
                  >
                    <q-icon size="26px" name="grid_view" />
                  </div>
                  <div
                    class="bg-color-1 q-px-sm br-sm text-dark q-py-xs grid-btn"
                    style="border: 2px solid #DEE2E7; border-left: none; border-top-left-radius: 0; border-bottom-left-radius: 0; "
                  >
                    <q-icon size="26px" name="view_list" />
                  </div>
                </div> -->
              </div>
            </div>
          </div>
        </div>
        <div class="row q-gutter-y-md q-col-gutter-x-md q-mt-sm">
          <div
            :class="
              gridModel == 'grid' ? 'col-xs-12 col-sm-6 col-md-4' : 'col-xs-12'
            "
            v-for="(item, index) in productList"
            :key="index"
          >
            <!-- Product list goes here -->
            <div class="product-item bg-white overflow-hidden br-6">
              <div class="row">
                <q-card class="my-card" style="width: 100%">
                  <q-card-section
                    class="items-center"
                    :horizontal="
                      gridModel == 'grid' ? $q.screen.lt.xs : !$q.screen.lt.sm
                    "
                  >
                    <q-card-section class="q-pa-sm">
                      <q-img
                        :width="
                          $q.screen.lt.md
                            ? '180px'
                            : gridModel == 'grid'
                            ? '100%'
                            : '230px'
                        "
                        style="object-fit: contain"
                        :src="item.image1"
                      />
                      <!-- <q-img
                          :width="$q.screen.lt.md ? '180px' : '230px'"
                          :src="item.image2"
                        /> -->
                      <!-- </div> -->
                    </q-card-section>
                    <q-card-section class="no-padding">
                      <div class="q-py-md q-px-sm relative-position">
                        <div
                          class="bg-white absolute-top-right br-6"
                          :style="
                            gridModel == 'grid'
                              ? { right: '0px', top: '15px' }
                              : $q.screen.lt.sm
                              ? { right: '0px', top: '15px' }
                              : { right: '20px', top: '20px' }
                          "
                          style="border: 2px solid #dee2e7"
                        >
                          <q-btn
                            flat
                            dense
                            color="primary"
                            :ripple="false"
                            size="1.2em"
                            icon="favorite_border"
                          />
                        </div>
                        <div>
                          <h5
                            class="product-item-grid-name overflow-hidden text-h5 fw-regular text-color-2 no-margin q-pt-x"
                            :class="
                              gridModel == 'grid'
                                ? 'hidden'
                                : 'visible' && $q.screen.gt.xs
                                ? gridModel == 'list'
                                  ? 'visible'
                                  : 'hidden'
                                : gridModel == 'list'
                                ? 'hidden'
                                : 'visible'
                            "
                          >
                            <a
                              href=""
                              class="text-color-2 product-title-link"
                              style="text-decoration: none"
                            >
                              {{ item.name }}
                            </a>
                          </h5>
                          <h4 class="text-h4 fw-medium text-color-2 no-margin">
                            $ {{ item.price }}
                          </h4>
                          <div class="flex">
                            <q-rating
                              v-model="item.rating"
                              max="5"
                              size="1.6em"
                              color="grey"
                              color-selected="deep-orange-7"
                              icon="star"
                              icon-selected="star"
                              readonly
                            />
                            <span
                              class="fs-16 fw-regular text-color-4 q-pl-sm"
                              >{{ item.rating }}</span
                            >
                            <span
                              class="fs-16 fw-light text-green-5 q-pl-md"
                              :class="
                                gridModel == 'grid'
                                  ? 'hidden'
                                  : 'visible' && $q.screen.gt.xs
                                  ? gridModel == 'list'
                                    ? 'visible'
                                    : 'hidden'
                                  : gridModel == 'list'
                                  ? 'hidden'
                                  : 'visible'
                              "
                              >Free Shipping</span
                            >
                          </div>
                          <div
                            class="bg-blue1 q-my-sm"
                            :class="
                              gridModel == 'grid'
                                ? 'hidden'
                                : 'visible' && $q.screen.gt.xs
                                ? gridModel == 'list'
                                  ? 'visible'
                                  : 'hidden'
                                : gridModel == 'list'
                                ? 'hidden'
                                : 'visible'
                            "
                            :style="
                              $q.screen.lt.md
                                ? { width: '100%' }
                                : { width: '80%' }
                            "
                          >
                            <p
                              class="fs-16 fw-light text-color-3 no-margin q-py-xs q-px-xs"
                            >
                              {{ item.discription }}
                            </p>
                          </div>
                          <q-btn
                            class="fw-regular"
                            :class="
                              gridModel == 'grid'
                                ? 'hidden'
                                : 'visible' && $q.screen.gt.xs
                                ? gridModel == 'list'
                                  ? 'visible'
                                  : 'hidden'
                                : gridModel == 'list'
                                ? 'hidden'
                                : 'visible'
                            "
                            no-caps
                            flat
                            color="primary"
                            label="View details"
                          />
                          <h5
                            class="product-item-name text-h5 fw-regular text-color-2 no-margin q-pt-md overflow-hidden"
                            :class="
                              gridModel == 'grid'
                                ? 'visible'
                                : 'hidden' && $q.screen.gt.xs
                                ? gridModel == 'list'
                                  ? 'hidden'
                                  : 'visible'
                                : gridModel == 'list'
                                ? 'visible'
                                : 'hidden'
                            "
                          >
                            <a
                              href=""
                              class="text-color-2 product-title-link"
                              style="text-decoration: none"
                            >
                              {{ item.name }}
                            </a>
                          </h5>
                        </div>
                      </div>
                    </q-card-section>
                  </q-card-section>

                  <!-- <q-separator />
                  <q-card-actions>
                    <q-btn flat round icon="event" />
                    <q-btn flat> 5:30PM </q-btn>
                    <q-btn flat> 7:00PM </q-btn>
                    <q-btn flat color="primary"> Reserve </q-btn>
                  </q-card-actions> -->
                </q-card>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ProductList from "src/pages/ProductList.vue";

export default {
  name: "Products",
  data() {
    return {
      color: false,
      gridModel: "list",
      ratingModel: "4.5",
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
        {
          id: "2",
          label: "Location",
          subcategories: [
            {
              id: "21",
              label: "Online",
              modelValue: false,
            },
            {
              id: "22",
              label: "Local Retailers",
              modelValue: false,
            },
          ],
        },
        {
          id: "3",
          label: "Made In",
          subcategories: [
            {
              id: "31",
              label: "United States",
              modelValue: false,
            },
            {
              id: "3",
              label: "United Kingdom",
              modelValue: false,
            },
            {
              id: "33",
              label: "Canada",
              modelValue: false,
            },
            {
              id: "34",
              label: "Pakistan",
              modelValue: false,
            },
            {
              id: "35",
              label: "Germany",
              modelValue: false,
            },
            {
              id: "36",
              label: "France",
              modelValue: false,
            },
            {
              id: "37",
              label: "Italy",
              modelValue: false,
            },
          ],
        },
        {
          id: "4",
          label: "Price",
          subcategories: [
            {
              id: "41",
              label: "$",
              label: "0 - $50",
              range: {
                min: 20,
                max: 65,
              },
            },
          ],
        },
        {
          id: "5",
          label: "Condition",
          subcategories: [
            {
              id: "51",
              label: "Any",
              modelValue: false,
            },
            {
              id: "52",
              label: "Used Item",
              modelValue: false,
            },
            {
              id: "53",
              label: "Refurbished",
              modelValue: false,
            },
            {
              id: "54",
              label: "Brand New",
              modelValue: false,
            },
          ],
        },
        {
          id: "6",
          label: "Rating",
          subcategories: [
            {
              id: "61",
              label: "1",
              ratingModel: 1,
              modelValue: false,
            },
            {
              id: "62",
              label: "2",
              ratingModel: 2,
              modelValue: false,
            },
            {
              id: "63",
              label: "3",
              ratingModel: 3,
              modelValue: false,
            },
            {
              id: "64",
              label: "4",
              ratingModel: 4,
              modelValue: false,
            },
            {
              id: "65",
              label: "5",
              ratingModel: 5,
              modelValue: false,
            },
          ],
        },
      ],
      productList: [
        {
          id: 1,
          name: "Canon EOS 2000, Black 10x zoom",
          price: 998,
          rating: 4.5,
          image1: "/images/tech/mobile-1.webp",
          image2: "/images/tech/mobile-2.webp",
          discription:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua",
        },
        {
          id: 2,
          name: "GoPro HERO6 4K Action Camera - Black",
          price: 1299,
          rating: 4.7,
          image1: "/images/tech/8.jpg",
          image2: "/images/tech/8.jpg",
          discription:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua",
        },
        {
          id: 3,
          name: "Nikon D850, Black and White",
          price: 1499,
          rating: 4.3,
          image1: "/images/tech/2.jpg",
          image2: "/images/tech/2.jpg",
          discription:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua",
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

.active-filter-item {
  background-color: #e5f1ff;
  color: #0067ff;
}

/* card section */
.grid-btn {
  transition: all 0.3s ease-in-out;
  &:hover {
    background-color: #0067ff;
    color: #ffffff;
    cursor: pointer;
  }
}
.my-custom-toggle {
  border: 2px solid #0067ff;
}

.product-item {
  transition: all 0.3s ease-in-out;
  border: 2px solid #dee2e7;
  &:hover {
    box-shadow: rgba(17, 17, 26, 0.1) 0px 0px 16px;
    cursor: pointer;
    border-color: #0066ff69;
  }
}
.product-item-grid-name {
  width: 80%;
  height: 33px;
  /* background: aqua; */
}

.product-item-name {
  height: 67px;
  line-height: 25px;
  /* background-color: red; */
}

.product-title-link {
  transition: all 0.3s ease-in-out;
  &:hover {
    color: #eb001b;
  }
}
</style>
