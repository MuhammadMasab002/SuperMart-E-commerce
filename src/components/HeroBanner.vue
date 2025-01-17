<template>
  <div class="container q-px-sm q-py-md">
    <div
      class="row justify-center items-cente bg-white br-6 q-py-sm"
      :class="$q.screen.lt.lg ? 'q-px-sm' : 'q-px-md'"
      style="border: 1px solid #dee2e7"
    >
      <div
        :class="
          $q.screen.lt.md ? 'hidden' : $q.screen.lt.lg ? 'col-3' : 'col visible'
        "
      >
        <q-list class="q-mr-md" dense>
          <q-item
            class="br-6 q-my-sm text-color-1"
            dense
            tag="a"
            v-ripple="false"
            v-for="(item, index) in categories"
            :key="index"
            :class="{
              active: hoverIndex === index,
              defaultActive: activeIndex === index && hoverIndex === null,
            }"
            @click="setActive(index)"
            @mouseover="setHover(index)"
            @mouseleave="clearHover"
          >
            <q-item-section>
              <q-item-label class="fs-14 fw-regular q-py-sm text-capitalize">{{
                item.name
              }}</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </div>
      <div
        :class="$q.screen.gt.md ? 'col-7' : $q.screen.gt.md ? 'col-7' : 'col'"
      >
        <div
          class="bg-banner q-py-xl text-color-2"
          :class="$q.screen.lt.md ? 'q-px-md' : 'q-px-xl'"
        >
          <div
            class="q-py-xl"
            :class="$q.screen.lt.sm ? 'q-my-none' : 'q-mb-xl q-mt-lg'"
          >
            <div class="fs-28 fw-light">Latest trending</div>
            <div class="fs-32 fw-semibold" style="line-height: 38px">
              Electronic items
            </div>
            <div class="q-mt-sm">
              <q-btn
                label="Learn more"
                v-ripple="false"
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
      <div class="col" :class="$q.screen.lt.lg ? 'hidden' : 'visible'">
        <div class="row q-pl-md q-gutter-y-sm">
          <div class="col-12">
            <div class="br-md bg-color-2 q-pa-md">
              <div class="flex justify-evenly items-center no-wrap">
                <q-avatar size="50px">
                  <img src="/images/icons/Avatar.png" alt="User Avatar" />
                </q-avatar>
                <p class="fs-18 fw-regular q-mb-none" style="line-height: 22px">
                  Hi, user
                  <br :class="$q.screen.lt.lg ? 'hidden' : 'visible'" />
                  let’s get stated
                </p>
              </div>
              <div class="q-gutter-y- q-mx-sm text-center">
                <q-btn
                  label="Join now"
                  v-ripple="false"
                  class="br-6 q-mt-md no-shadow"
                  style="width: 100%; background-color: #0d6efd; color: #fff"
                />
                <q-btn
                  label="Log in"
                  v-ripple="false"
                  class="br-6 q-mt-sm"
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
          <div class="col-12">
            <div class="br-md bg-color-3 q-py-md q-px-lg text-white">
              <p class="fs-22 fw-light q-mb-none" style="line-height: 23px">
                Get US $10 off <br />
                with a new <br />
                supplier
              </p>
            </div>
          </div>
          <div class="col-12">
            <div class="br-md bg-color-4 q-py-md q-px-lg text-white">
              <p class="fs-22 fw-light q-mb-none" style="line-height: 23px">
                Send quotes with
                <br :class="$q.screen.lt.lg ? 'hidden' : 'visible'" />
                supplier <br />
                preferences
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CustomListItem",
  data() {
    return {
      activeIndex: 0, // Default active item
      hoverIndex: null, // Tracks the item being hovered
      // LinkList: [

      //   { label: "Electronics", route: "/electronics" },
      //   { label: "Clothes and wear", route: "/clothesWear" },
      //   { label: "Home interiors", route: "/homeInterior" },
      //   { label: "Computer and tech", route: "/tech" },
      //   { label: "Health & Fitness", route: "/healthFitness" },
      //   { label: "Sports and outdoor", route: "/sportOutdoor" },
      //   { label: "Beauty & Personal Care", route: "/personalCare" },
      //   { label: "Books & Stationery", route: "/bookStationery" },
      //   { label: "More category", route: "/moreCategory" },
      // ],

      categories: [
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
        {
          id: 9,
          name: "All Categories",
          link: "/all-categories",
          // subcategories: []
        }
      ],
    };
  },
  methods: {
    setActive(index) {
      this.activeIndex = index; // Update active item on click
    },
    setHover(index) {
      this.hoverIndex = index; // Temporarily make hovered item active
    },
    clearHover() {
      this.hoverIndex = null; // Revert to default active item
    },
  },
};
</script>

<style scoped>
.q-item {
  transition: background-color 0.2s ease, color 0.2s ease;
  cursor: pointer;
}

/* Hovered or Clicked Item */
.q-item.active {
  color: #1c1c1c; /* Same as hover text color */
  background-color: #e5f1ff; /* Same as hover background color */
}

/* Default Active Item (When no hover is active) */
.q-item.defaultActive {
  color: #1c1c1c;
  background-color: #e5f1ff;
}

/* Inactive Items */
.q-item:not(.active):not(.defaultActive):hover {
  color: #1c1c1c;
  background-color: #e5f1ff;
}

.q-btn:before {
  box-shadow: none;
}

.bg-banner {
  width: 100%;
  height: 100%;
  content: "";
  background-image: url(/images/banners/Banner-board-800x420.png);
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
