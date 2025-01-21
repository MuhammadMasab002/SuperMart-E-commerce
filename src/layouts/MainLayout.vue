<template>
  <q-layout view="lHh Lpr fff ">
    <!--  * hHh lpR fff-->
    <q-header elevate class="bg-white">
      <div style="border-bottom: 1px solid #e0e0e0">
        <div class="container" :class="$q.screen.lt.sm ? 'q-px-sm' : 'q-px-md'">
          <q-toolbar class="justify-between q-py-md" style="width: 100%">
            <div class="flex justify-center items-center">
              <div
                class="q-mr-md"
                :class="$q.screen.lt.md ? 'visible' : 'hidden'"
              >
                <q-btn
                  class="text-black"
                  flat
                  dense
                  round
                  icon="menu"
                  aria-label="Menu"
                  @click="toggleLeftDrawer"
                />
              </div>
              <div>
                <a href="#">
                  <q-img
                    :width="$q.screen.lt.sm ? '135px' : '150px'"
                    height="auto"
                    src="/images/logo/logo-colored.png"
                  />
                </a>
              </div>
            </div>
            <div
              class="br-md flex bg-white"
              :class="$q.screen.lt.md ? 'hidden' : 'visible'"
              style="border: 2px solid #0d6efd"
            >
              <q-input
                class="br-md q-px-sm"
                style="min-width: 450px"
                borderless
                square
                v-model="search"
                dense
                placeholder="Search"
                clearable
              />
              <!-- <div>
                <q-select
                  class="q-px-sm"
                  style="
                    min-width: 150px;
                    border-left: 1px solid #0d6efd;
                    border-right: 1px solid #0d6efd;
                  "
                  square
                  dense
                  borderless
                  v-model="category_selected"
                  :options="categoryOptions"
                  option-value="name"
                  option-label="name"
                  label="All Categories"
                  transition-show="jump-up"
                  transition-hide="jump-up"
                >
                </q-select>
              </div> -->
              <q-btn
                class="br-right q-px-lg bg-color-gradient text-white"
                unelevated
                label="Search"
                :ripple="false"
              />
            </div>
            <div>
              <q-list
                class="flex text-dark"
                :class="$q.screen.lt.sm ? 'q-gutter-x-none' : 'q-gutter-x-sm'"
                bordere
                dense
              >
                <q-item class="no-padding nav-items">
                  <q-item-section>
                    <q-avatar square size="44px">
                      <q-icon name="person" />
                      <q-item-label
                        captio
                        class="fs-10 fw-light"
                        :class="$q.screen.lt.sm ? 'hidden' : 'visible'"
                        >Profile</q-item-label
                      >
                    </q-avatar>
                  </q-item-section>
                </q-item>
                <q-item
                  class="no-padding nav-items"
                  :class="$q.screen.gt.xs ? 'visible' : 'hidden'"
                >
                  <q-item-section>
                    <q-avatar square size="44px">
                      <q-icon name="message" />
                      <q-item-label class="fs-10 fw-light"
                        >Message</q-item-label
                      >
                    </q-avatar>
                  </q-item-section>
                </q-item>
                <q-item
                  class="no-padding nav-items"
                  :class="$q.screen.gt.xs ? 'visible' : 'hidden'"
                >
                  <q-item-section>
                    <q-avatar square size="44px">
                      <q-icon name="favorite" />
                      <q-item-label class="fs-10 fw-light">Orders</q-item-label>
                    </q-avatar>
                  </q-item-section>
                </q-item>
                <q-item class="no-padding nav-items">
                  <q-item-section>
                    <q-avatar square size="44px">
                      <q-icon name="shopping_cart" />
                      <q-item-label
                        class="fs-10 fw-light"
                        :class="$q.screen.lt.sm ? 'hidden' : 'visible'"
                        >My Cart</q-item-label
                      >
                    </q-avatar>
                  </q-item-section>
                </q-item>
              </q-list>
            </div>
          </q-toolbar>
        </div>
      </div>
      <div style="border-bottom: 1px solid #e0e0e0">
        <div class="container q-px-md">
          <div class="row" :class="$q.screen.lt.md ? 'hidden' : 'visible'">
            <div class="col-8">
              <q-list class="flex q-py-sm text-dark" bordere dense>
                <q-item class="no-padding q-mx-xs nav-items">
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular q-px-sm"
                      >All category</q-item-label
                    >
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-xs nav-items">
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular q-px-sm"
                      >Hot offers</q-item-label
                    >
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-xs nav-items">
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular q-px-sm"
                      >Gift boxes</q-item-label
                    >
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-xs nav-items">
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular q-px-sm"
                      >Projects</q-item-label
                    >
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-xs nav-items">
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular q-px-sm"
                      >Menu item</q-item-label
                    >
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-sm">
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular">
                      <q-select
                        class="q-px-sm br-sm nav-select-option"
                        style="min-width: 120px"
                        square
                        dense
                        borderless
                        v-model="helps_selected"
                        :options="helps"
                        label="Help"
                        transition-show="jump-up"
                        transition-hide="jump-up"
                      />
                    </q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>
            </div>
            <div class="col flex justify-end items-center">
              <q-list class="flex text-dark" bordere dense>
                <q-item class="no-padding q-mx-s" clickabl>
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular">
                      <q-select
                        class="q-px-sm br-sm nav-select-option"
                        style="min-width: 140px"
                        square
                        dense
                        borderless
                        v-model="currency_selected"
                        :options="currency"
                        option-value="currency"
                        option-label="currency"
                        label="Currency"
                        transition-show="jump-up"
                        transition-hide="jump-up"
                      >
                        <!-- <template v-slot:append>
                          <q-avatar square class="q-ml-sm">
                            <q-img :src="selected ? selected.flag : ''" />
                          </q-avatar>
                        </template> -->
                      </q-select>
                    </q-item-label>
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-md" clickabl>
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular">
                      <q-select
                        class="q-px-sm br-sm nav-select-option"
                        style="min-width: 120px"
                        square
                        dense
                        borderless
                        v-model="shipTo_selected"
                        :options="shipTo"
                        option-value="ship"
                        option-label="ship"
                        label="Ship to"
                        transition-show="jump-up"
                        transition-hide="jump-up"
                      >
                        <template v-slot:append>
                          <q-avatar square>
                            <q-img
                              :src="shipTo_selected ? shipTo_selected.flag : ''"
                            />
                          </q-avatar>
                        </template>
                      </q-select>
                    </q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>
            </div>
          </div>
          <div
            class="row justify-center q-py-md"
            :class="$q.screen.lt.md ? 'visible' : 'hidden'"
          >
            <div class="col">
              <div class="br-md bg-white flex justify-center items-center">
                <q-input
                  class="q-px-sm"
                  :class="$q.screen.lt.sm ? 'br-6' : 'br-left'"
                  style="border: 2px solid #0d6efd"
                  :style="
                    $q.screen.lt.sm ? { width: '100%' } : { width: '35%' }
                  "
                  borderless
                  square
                  v-model="search"
                  dense
                  placeholder="Search"
                  clearable
                >
                  <template v-if="$q.screen.lt.sm" v-slot:prepend>
                    <q-icon name="search" />
                  </template>
                </q-input>
                <div
                  class="flex justify-center"
                  :class="$q.screen.lt.sm ? 'hidden' : 'visible'"
                >
                  <q-select
                    class="q-px-sm"
                    style="
                      min-width: 150px;
                      border: 2px solid #0d6efd;
                      border-left: none;
                    "
                    square
                    dense
                    borderless
                    v-model="category_selected"
                    :options="categoryOptions"
                    option-value="name"
                    option-label="name"
                    label="All Categories"
                    transition-show="jump-up"
                    transition-hide="jump-up"
                  />
                  <q-btn
                    class="br-right bg-color-gradient text-white"
                    unelevated
                    label="Search"
                    :ripple="false"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" bordered>
      <q-list>
        <q-item-label header>
          <div class="br-md bg-color-2 q-pa-md">
            <div class="flex justify-center items-center no-wrap">
              <q-avatar size="50px">
                <img src="/images/icons/Avatar.png" alt="User Avatar" />
              </q-avatar>
            </div>
            <div class="q-gutter-y-md q-mt-md">
              <div>
                <q-btn
                  label="Sign in"
                  v-ripple="false"
                  class="br-6 no-shadow"
                  style="width: 100%; background-color: #0d6efd; color: #fff"
                />
              </div>
              <div>
                <q-btn
                  label="Register"
                  v-ripple="false"
                  class="br-6"
                  style="
                    width: 100%;
                    background-color: #fff;
                    color: #0d6efd;
                    border: 1px solid #0d6efd;
                  "
                />
              </div>
            </div>
          </div>
        </q-item-label>

        <EssentialLink
          class="text-blac"
          v-for="link in dynamicLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <!-- footer section -->
    <q-footer>
      <div class="bg-white q-py-lg">
        <div class="container q-px-sm q-py-lg">
          <div
            class="row"
            :class="$q.screen.lt.md ? 'text-center' : 'text-left'"
          >
            <div class="col-xs-12 col-md-3">
              <div>
                <q-img
                  width="140px"
                  height="auto"
                  src="/images/logo/logo-colored.png"
                />
              </div>
              <div>
                <p class="fs-16 fw-regulat text-color-1 no-margin q-pt-md">
                  Best information about the company gies <br :class="$q.screen.lt.md ? 'visible': 'hidden'">
                  here but now lorem ipsum is
                </p>
              </div>
              <ul
                class="flex q-gutter-x-sm no-padding q-my-md"
                :class="$q.screen.lt.md ? 'flex-center' : 'items-center'"
              >
                <li class="footer-icon br-xl flex flex-center">
                  <q-icon name="fab fa-facebook" color="white" size="20px" />
                </li>
                <li class="footer-icon br-xl flex flex-center">
                  <q-icon name="fab fa-twitter" color="white" size="20px" />
                </li>
                <li class="footer-icon br-xl flex flex-center">
                  <q-icon name="fab fa-linkedin" color="white" size="20px" />
                </li>
                <li class="footer-icon br-xl flex flex-center">
                  <q-icon name="fab fa-instagram" color="white" size="20px" />
                </li>
                <li class="footer-icon br-xl flex flex-center">
                  <q-icon name="fab fa-youtube" color="white" size="20px" />
                </li>
              </ul>

              <!-- <div>
              <p class="fs-16 fw-light text-color-3 no-margin q-py-sm">
                Address: 123 Main Street, City, State, Zip
              </p>
              <p class="fs-16 fw-light text-color-3 no-margin q-py-sm">
                Phone: (123) 456-7890
              </p>
            </div> -->
            </div>
            <div class="col-xs-12 col-md-6">
              <div
                class="row"
                :class="$q.screen.lt.md ? 'q-my-md q-px-none' : 'q-px-sm'"
              >
                <div
                  class="col-xs-12 col-sm-4"
                  v-for="(item, index) in nevigations"
                  :key="index"
                >
                  <div>
                    <h5
                      class="text-h5 text-color-2 fw-medium no-margin q-py-none"
                      :class="$q.screen.lt.md ? 'q-pl-none' : 'q-pl-md'"
                    >
                      {{ item.label }}
                    </h5>
                    <q-list dense padding class="text-color-3 fs-16">
                      <q-item
                        clickabl
                        class="footer-items"
                        v-for="(link, index) in item.links"
                        :key="index"
                      >
                        <q-item-section> {{ link.label }} </q-item-section>
                      </q-item>
                    </q-list>
                  </div>
                </div>
              </div>
            </div>
            <div class="col-xs-12 col-md-3">
              <div>
                <h5
                  class="text-h5 text-color-2 fw-medium no-margin q-pb-md"
                  :class="$q.screen.lt.md ? 'q-pl-none' : 'q-pl-md'"
                >
                  Get App
                </h5>
                <div class="q-py-xs">
                  <q-img
                    class="store-img"
                    width="130px"
                    height="auto"
                    src="/images/Misc/app_store.png"
                  />
                </div>
                <div class="q-py-xs">
                  <q-img
                    class="store-img"
                    width="130px"
                    height="auto"
                    src="/images/Misc/play_store.png"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="bg-color-1 q-py-lg">
        <footer class="container q-px-sm">
          <!-- copyright section -->
          <div
            class="row items-center"
            :class="$q.screen.lt.sm ? 'justify-center' : 'justify-between'"
          >
            <div :class="$q.screen.lt.sm ? 'col-xs-12' : 'col'">
              <p
                class="fs-14 fw-light text-color-5 no-margin"
                :class="$q.screen.lt.sm ? 'text-center' : 'text-left'"
              >
                &copy; 2023 Ecommerce. All rights reserved.
              </p>
            </div>
            <div
              class="col-auto text-center"
              :class="$q.screen.lt.sm ? 'q-pt-md' : ''"
            >
              <q-select
                class="q-px-sm br-sm nav-select-option"
                style="min-width: 120px"
                square
                dense
                borderless
                v-model="selected"
                :options="languages"
                option-value="country"
                option-label="country"
                label="Lang"
                transition-show="jump-up"
                transition-hide="jump-up"
              >
                <template v-slot:append>
                  <q-avatar square class="q-ml-sm">
                    <q-img :src="selected ? selected.flag : ''" />
                  </q-avatar>
                </template>
              </q-select>
            </div>
            <!-- <div>
            <a href="#" class="text-color-5">
              <q-icon name="facebook" />
            </a>
            <a href="#" class="text-color-5">
              <q-icon name="twitter" />
            </a>
            <a href="#" class="text-color-5">
              <q-icon name="instagram" />
            </a>
            <a href="#" class="text-color-5">
              <q-icon name="linkedin" />
            </a>
          </div> -->
          </div>
        </footer>
      </div>
    </q-footer>
  </q-layout>
</template>

<script>
//import { ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";

export default {
  components: {
    EssentialLink,
  },
  data() {
    return {
      leftDrawerOpen: false,

      search: "", // Added for q-input
      category_selected: null,
      subcategory_selected: null,
      helps_selected: null,
      currency_selected: null,
      shipTo_selected: null,
      // categories: [
      //   "Electronics",
      //   "Fashion",
      //   "Home & Kitchen",
      //   "Beauty & Personal Care",
      //   "Health & Fitness",
      //   "Baby & Kids",
      //   "Books & Stationery",
      //   "Sports & Outdoors",
      // ],
      categoryOptions: [
        {
          id: 1,
          name: "Electronics",
          link: "/electronics",
          subcategories: [
            {
              id: 101,
              name: "Mobile Phones",
              link: "/electronics/mobile-phones",
              subcategories: [
                {
                  id: 1011,
                  name: "Smartphones",
                  link: "/electronics/mobile-phones/smartphones",
                },
                {
                  id: 1012,
                  name: "Feature Phones",
                  link: "/electronics/mobile-phones/feature-phones",
                },
                {
                  id: 1013,
                  name: "Accessories",
                  link: "/electronics/mobile-phones/accessories",
                }, // Cases, Chargers, Screen Protectors
              ],
            },
            {
              id: 102,
              name: "Computers & Laptops",
              link: "/electronics/computers-laptops",
              subcategories: [
                {
                  id: 1021,
                  name: "Desktops",
                  link: "/electronics/computers-laptops/desktops",
                },
                {
                  id: 1022,
                  name: "Laptops",
                  link: "/electronics/computers-laptops/laptops",
                },
                {
                  id: 1023,
                  name: "Monitors",
                  link: "/electronics/computers-laptops/monitors",
                },
              ],
            },
            {
              id: 103,
              name: "Wearable Tech",
              link: "/electronics/wearable-tech",
              subcategories: [
                {
                  id: 1031,
                  name: "Smartwatches",
                  link: "/electronics/wearable-tech/smartwatches",
                },
                {
                  id: 1032,
                  name: "Fitness Bands",
                  link: "/electronics/wearable-tech/fitness-bands",
                },
              ],
            },
            {
              id: 104,
              name: "Audio Devices",
              link: "/electronics/audio-devices",
              subcategories: [
                {
                  id: 1041,
                  name: "Headphones",
                  link: "/electronics/audio-devices/headphones",
                },
                {
                  id: 1042,
                  name: "Earbuds",
                  link: "/electronics/audio-devices/earbuds",
                },
                {
                  id: 1043,
                  name: "Speakers",
                  link: "/electronics/audio-devices/speakers",
                },
              ],
            },
          ],
        },
        {
          id: 2,
          name: "Fashion",
          link: "/fashion",
          subcategories: [
            {
              id: 201,
              name: "Men's Clothing",
              link: "/fashion/mens-clothing",
              subcategories: [
                { id: 2011, name: "Tops", link: "/fashion/mens-clothing/tops" },
                {
                  id: 2012,
                  name: "Bottoms",
                  link: "/fashion/mens-clothing/bottoms",
                },
                {
                  id: 2013,
                  name: "Outerwear",
                  link: "/fashion/mens-clothing/outerwear",
                },
              ],
            },
            {
              id: 202,
              name: "Women's Clothing",
              link: "/fashion/womens-clothing",
              subcategories: [
                {
                  id: 2021,
                  name: "Tops",
                  link: "/fashion/womens-clothing/tops",
                },
                {
                  id: 2022,
                  name: "Dresses",
                  link: "/fashion/womens-clothing/dresses",
                },
                {
                  id: 2023,
                  name: "Bottoms",
                  link: "/fashion/womens-clothing/bottoms",
                },
              ],
            },
            {
              id: 203,
              name: "Accessories",
              link: "/fashion/accessories",
              subcategories: [
                { id: 2031, name: "Belts", link: "/fashion/accessories/belts" },
                {
                  id: 2032,
                  name: "Sunglasses",
                  link: "/fashion/accessories/sunglasses",
                },
                { id: 2033, name: "Hats", link: "/fashion/accessories/hats" },
              ],
            },
          ],
        },
        {
          id: 3,
          name: "Home & Kitchen",
          link: "/home-kitchen",
          subcategories: [
            {
              id: 301,
              name: "Furniture",
              link: "/home-kitchen/furniture",
              subcategories: [
                {
                  id: 3011,
                  name: "Beds",
                  link: "/home-kitchen/furniture/beds",
                },
                {
                  id: 3012,
                  name: "Sofas",
                  link: "/home-kitchen/furniture/sofas",
                },
                {
                  id: 3013,
                  name: "Dining Tables",
                  link: "/home-kitchen/furniture/dining-tables",
                },
              ],
            },
            {
              id: 302,
              name: "Kitchen Appliances",
              link: "/home-kitchen/kitchen-appliances",
              subcategories: [
                {
                  id: 3021,
                  name: "Blenders",
                  link: "/home-kitchen/kitchen-appliances/blenders",
                },
                {
                  id: 3022,
                  name: "Microwaves",
                  link: "/home-kitchen/kitchen-appliances/microwaves",
                },
                {
                  id: 3023,
                  name: "Refrigerators",
                  link: "/home-kitchen/kitchen-appliances/refrigerators",
                },
              ],
            },
            {
              id: 303,
              name: "Home Decor",
              link: "/home-kitchen/home-decor",
              subcategories: [
                {
                  id: 3031,
                  name: "Wall Art",
                  link: "/home-kitchen/home-decor/wall-art",
                },
                {
                  id: 3032,
                  name: "Lamps",
                  link: "/home-kitchen/home-decor/lamps",
                },
                {
                  id: 3033,
                  name: "Curtains",
                  link: "/home-kitchen/home-decor/curtains",
                },
              ],
            },
          ],
        },
        {
          id: 4,
          name: "Beauty & Personal Care",
          link: "/beauty-personal-care",
          subcategories: [
            {
              id: 401,
              name: "Skin Care",
              link: "/beauty-personal-care/skin-care",
              subcategories: [
                {
                  id: 4011,
                  name: "Moisturizers",
                  link: "/beauty-personal-care/skin-care/moisturizers",
                },
                {
                  id: 4012,
                  name: "Cleansers",
                  link: "/beauty-personal-care/skin-care/cleansers",
                },
                {
                  id: 4013,
                  name: "Sunscreen",
                  link: "/beauty-personal-care/skin-care/sunscreen",
                },
              ],
            },
            {
              id: 402,
              name: "Hair Care",
              link: "/beauty-personal-care/hair-care",
              subcategories: [
                {
                  id: 4021,
                  name: "Shampoos",
                  link: "/beauty-personal-care/hair-care/shampoos",
                },
                {
                  id: 4022,
                  name: "Conditioners",
                  link: "/beauty-personal-care/hair-care/conditioners",
                },
                {
                  id: 4023,
                  name: "Hair Oils",
                  link: "/beauty-personal-care/hair-care/hair-oils",
                },
              ],
            },
            {
              id: 403,
              name: "Makeup",
              link: "/beauty-personal-care/makeup",
              subcategories: [
                {
                  id: 4031,
                  name: "Lipsticks",
                  link: "/beauty-personal-care/makeup/lipsticks",
                },
                {
                  id: 4032,
                  name: "Foundations",
                  link: "/beauty-personal-care/makeup/foundations",
                },
                {
                  id: 4033,
                  name: "Eye Makeup",
                  link: "/beauty-personal-care/makeup/eye-makeup",
                },
              ],
            },
          ],
        },
        {
          id: 5,
          name: "Health & Fitness",
          link: "/health-fitness",
          subcategories: [
            {
              id: 501,
              name: "Exercise Equipment",
              link: "/health-fitness/exercise-equipment",
              subcategories: [
                {
                  id: 5011,
                  name: "Dumbbells",
                  link: "/health-fitness/exercise-equipment/dumbbells",
                },
                {
                  id: 5012,
                  name: "Resistance Bands",
                  link: "/health-fitness/exercise-equipment/resistance-bands",
                },
                {
                  id: 5013,
                  name: "Treadmills",
                  link: "/health-fitness/exercise-equipment/treadmills",
                },
              ],
            },
            {
              id: 502,
              name: "Yoga Essentials",
              link: "/health-fitness/yoga-essentials",
              subcategories: [
                {
                  id: 5021,
                  name: "Mats",
                  link: "/health-fitness/yoga-essentials/mats",
                },
                {
                  id: 5022,
                  name: "Blocks",
                  link: "/health-fitness/yoga-essentials/blocks",
                },
                {
                  id: 5023,
                  name: "Straps",
                  link: "/health-fitness/yoga-essentials/straps",
                },
              ],
            },
            {
              id: 503,
              name: "Supplements",
              link: "/health-fitness/supplements",
              subcategories: [
                {
                  id: 5031,
                  name: "Protein Powders",
                  link: "/health-fitness/supplements/protein-powders",
                },
                {
                  id: 5032,
                  name: "Vitamins",
                  link: "/health-fitness/supplements/vitamins",
                },
                {
                  id: 5033,
                  name: "Energy Bars",
                  link: "/health-fitness/supplements/energy-bars",
                },
              ],
            },
          ],
        },
        {
          id: 6,
          name: "Baby & Kids",
          link: "/baby-kids",
          subcategories: [
            {
              id: 601,
              name: "Toys",
              link: "/baby-kids/toys",
              subcategories: [
                {
                  id: 6011,
                  name: "Educational Toys",
                  link: "/baby-kids/toys/educational-toys",
                },
                {
                  id: 6012,
                  name: "Board Games",
                  link: "/baby-kids/toys/board-games",
                },
              ],
            },
            {
              id: 602,
              name: "Clothing",
              link: "/baby-kids/clothing",
              subcategories: [
                {
                  id: 6021,
                  name: "Boys' Clothing",
                  link: "/baby-kids/clothing/boys-clothing",
                },
                {
                  id: 6022,
                  name: "Girls' Clothing",
                  link: "/baby-kids/clothing/girls-clothing",
                },
                {
                  id: 6023,
                  name: "Infant Clothing",
                  link: "/baby-kids/clothing/infant-clothing",
                },
              ],
            },
          ],
        },
        {
          id: 7,
          name: "Books & Stationery",
          link: "/books-stationery",
          subcategories: [
            {
              id: 701,
              name: "Books",
              link: "/books-stationery/books",
              subcategories: [
                {
                  id: 7011,
                  name: "Fiction",
                  link: "/books-stationery/books/fiction",
                },
                {
                  id: 7012,
                  name: "Non-Fiction",
                  link: "/books-stationery/books/non-fiction",
                },
                {
                  id: 7013,
                  name: "Children's Books",
                  link: "/books-stationery/books/childrens-books",
                },
              ],
            },
            {
              id: 702,
              name: "Stationery",
              link: "/books-stationery/stationery",
              subcategories: [
                {
                  id: 7021,
                  name: "Pens",
                  link: "/books-stationery/stationery/pens",
                },
                {
                  id: 7022,
                  name: "Pencils",
                  link: "/books-stationery/stationery/pencils",
                },
                {
                  id: 7023,
                  name: "Markers",
                  link: "/books-stationery/stationery/markers",
                },
              ],
            },
          ],
        },
        {
          id: 8,
          name: "Sports & Outdoors",
          link: "/sports-outdoors",
          subcategories: [
            {
              id: 801,
              name: "Sports Equipment",
              link: "/sports-outdoors/sports-equipment",
              subcategories: [
                {
                  id: 8011,
                  name: "Soccer Balls",
                  link: "/sports-outdoors/sports-equipment/soccer-balls",
                },
                {
                  id: 8012,
                  name: "Basketballs",
                  link: "/sports-outdoors/sports-equipment/basketballs",
                },
                {
                  id: 8013,
                  name: "Nets",
                  link: "/sports-outdoors/sports-equipment/nets",
                },
              ],
            },
            {
              id: 802,
              name: "Outdoor Clothing",
              link: "/sports-outdoors/outdoor-clothing",
              subcategories: [
                {
                  id: 8021,
                  name: "Soccer Shirts",
                  link: "/sports-outdoors/outdoor-clothing/soccer-shirts",
                },
                {
                  id: 8022,
                  name: "Jerseys",
                  link: "/sports-outdoors/outdoor-clothing/jerseys",
                },
                {
                  id: 8023,
                  name: "Shorts",
                  link: "/sports-outdoors/outdoor-clothing/shorts",
                },
              ],
            },
          ],
        },
      ],
      helps: [
        "Help Center",
        "Privacy Policy",
        "Term & Conditions",
        "FAQ's",
        "Contact Us",
      ],
      currency: ["English, USD", "French EUR", "Spanish, USD", "Russian, RUB"],
      shipTo: [
        {
          id: "1",
          ship: "DE",
          flag: "/images/flags/9=DE.png",
          // link: "shopname.cn",
        },
        {
          id: "2",
          ship: "UK",
          flag: "/images/flags/10=GB.png",
          // link: "shopname.gb",
        },
        {
          id: "3",
          ship: "UAE",
          flag: "/images/flags/1=AE.png",
          // link: "shopname.fr",
        },
        {
          id: "4",
          ship: "USA",
          flag: "/images/flags/3=US.png",
          // link: "shopname.it",
        },
      ],
      dynamicLinks: [],
      linksList: [
        {
          title: "Home",
          // caption: "quasar.dev",
          icon: "home",
          // link: "https://quasar.dev",
        },
        {
          title: "Categories",
          icon: "list",
          subcategories: [
            {
              id: 1,
              name: "Electronics",
              icon: "devices",
              link: "/electronics",
            },
            {
              id: 2,
              name: "Fashion",
              icon: "style",
              link: "/fashion",
            },
            {
              id: 3,
              name: "Home & Kitchen",
              icon: "kitchen",
              link: "/home-kitchen",
            },
            {
              id: 4,
              name: "Beauty & Personal Care",
              icon: "spa",
              link: "/beauty-personal-care",
            },
            {
              id: 5,
              name: "Health & Fitness",
              icon: "fitness_center",
              link: "/health-fitness",
            },
            {
              id: 6,
              name: "Baby & Kids",
              icon: "child_care",
              link: "/baby-kids",
            },
            {
              id: 7,
              name: "Books & Stationery",
              icon: "menu_book",
              link: "/books-stationery",
            },
            {
              id: 8,
              name: "Sports & Outdoors",
              icon: "sports",
              link: "/sports-outdoors",
            },
          ],
          // caption: "github.com/quasarframework",
          // link: "https://github.com/quasarframework",
        },
        {
          title: "Favorites",
          // caption: "chat.quasar.dev",
          icon: "favorite",
          // link: "https://chat.quasar.dev",
        },
        {
          title: "My Orders",
          // caption: "forum.quasar.dev",
          icon: "inventory",
          // link: "https://forum.quasar.dev",
        },
        {
          title: "Currency",
          // caption: "@quasarframework",
          icon: "currency_exchange",
          subcategories: [
            {
              id: 1,
              name: "English, USD",
              flag: "/images/flags/10=GB.png",
            },
            {
              id: 2,
              name: "French, EUR",
              flag: "/images/flags/7=FR.png",
            },
            {
              id: 3,
              name: "Spanish, USD",
              flag: "/images/flags/11=SP.png",
            },
            {
              id: 4,
              name: "Russian, RUB",
              flag: "/images/flags/4=RU.png",
            },
          ],
          // link: "https://twitter.quasar.dev",
        },
        {
          title: "Contact Us",
          // caption: "@QuasarFramework",
          icon: "headset_mic",
          // link: "https://facebook.quasar.dev",
        },
        {
          title: "About Us",
          // caption: "Community Quasar projects",
          icon: "info",
          // link: "https://awesome.quasar.dev",
        },
        {
          title: "User Aggregation",
          // caption: "Community Quasar projects",
          icon: "group_add",
          // link: "https://awesome.quasar.dev",
        },
        {
          title: "Partnerships",
          // caption: "Community Quasar projects",
          icon: "handshake",
          // link: "https://awesome.quasar.dev",
        },
        {
          title: "Privacy Policy",
          // caption: "Community Quasar projects",
          icon: "lock",
          // link: "https://awesome.quasar.dev",
        },
      ],

      //// footer part
      selected: null,
      languages: [
        {
          id: "1",
          country: "English",
          flag: "/images/flags/10=GB.png",
          // link: "shopname.gb",
        },
        {
          id: "2",
          country: "French",
          flag: "/images/flags/7=FR.png",
          // link: "shopname.fr",
        },
        {
          id: "3",
          country: "Chinese",
          flag: "/images/flags/8=CN.png",
          // link: "shopname.cn",
        },
        {
          id: "4",
          country: "Italian",
          flag: "/images/flags/5=IT.png",
          // link: "shopname.it",
        },
      ],
      nevigations: [
        {
          label: "Nevigation",
          links: [
            {
              label: "About us",
              href: "#about",
            },
            {
              label: "Find Store",
              href: "#store",
            },
            {
              label: "Categories",
              href: "#categories",
            },
            {
              label: "Blogs",
              href: "#blogs",
            },
          ],
        },
        {
          label: "Need Help?",
          links: [
            {
              label: "Help Center",
              href: "#help",
            },
            {
              label: "Money Refund",
              href: "#refund",
            },
            {
              label: "Shipping",
              href: "#shipping",
            },
            {
              label: "Contact us",
              href: "#contact",
            },
          ],
        },
        {
          label: "For users",
          links: [
            {
              label: "Login",
              href: "#login",
            },
            {
              label: "Register",
              href: "#register",
            },
            {
              label: "Settings",
              href: "#settings",
            },
            {
              label: "My Orders",
              href: "#orders",
            },
          ],
        },
      ],
    };
  },
  methods: {
    toggleLeftDrawer() {
      this.dynamicLinks = this.linksList;
      this.leftDrawerOpen = !this.leftDrawerOpen;
    },
  },
};
</script>

<style scoped>
.custom-input {
  width: 100%;
}
.nav-items {
  color: #000;
  background-color: transparent;
  transition: all 0.3s ease-in-out;

  &:hover {
    background-color: #e5f1ff;
    color: #0067ff;
    cursor: pointer;
  }
  .q-icon {
    color: gray;
    transition: all 0.3s ease-in-out;
  }
  &:hover {
    .q-icon {
      padding-bottom: 5px;
      color: #0067ff;
    }
  }
}
.nav-select-option {
  border: 1px solid #8b96a5;
  transition: all 0.3s ease-in-out;

  &:hover {
    border-color: #0067ff;
  }
}

/* footer secton */
.footer-items {
  transition: all 0.3s ease-in-out;
}
.footer-items:hover {
  padding-left: 20px;
  color: #0067ff;
  background-color: #e5f1ff;
  transform: scale(1.01);
  cursor: pointer;
}
.footer-icon {
  width: 35px;
  height: 35px;
  background-color: #bdc4cd;
  transition: all 0.3s ease-in-out;
}
.footer-icon:hover {
  background-color: #0067ff;
  transform: scale(1.1);
  cursor: pointer;
}

.store-img {
  transition: all 0.3s ease-in-out;
}
.store-img:hover {
  cursor: pointer;
}

.nav-select-option {
  border: 1px solid #8b96a5;
  transition: all 0.3s ease-in-out;

  &:hover {
    border-color: #0067ff;
  }
}
</style>
