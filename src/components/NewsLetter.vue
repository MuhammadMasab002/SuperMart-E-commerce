<template>
  <div class="bg-color-1 q-py-lg q-px-sm">
    <div class="column q-py-lg">
      <div class="q-pb-sm text-center">
        <h4
          class="text-h4 text-color-2 fw-medium no-margin q-py-none"
          style="line-height: 28px"
        >
          Subscribe on our newsletter
        </h4>
        <p class="fs-16 fw-light text-color-5 no-margin q-py-sm">
          Get daily news on upcoming offers from many suppliers all over the
          world
        </p>
      </div>
      <div class="row flex-center">
        <form @submit.prevent="submitForm">
          <div class="flex flex-center">
            <div class="q-field">
              <q-input
                id="email"
                v-model="email"
                type="email"
                outlined
                bg-color="white"
                filled="red"
                dense
                class="text-input q-px-sm br-6"
                placeholder="Enter your email address"
              >
                <template v-slot:prepend>
                  <q-icon name="mail" />
                </template>
              </q-input>
            </div>
            <div class="text-center">
              <q-btn
                type="submit"
                dense
                :ripple="false"
                class="bg-color-gradient text-white q-px-md q-py-sm br-6"
              >
                Subscribe
              </q-btn>
              <!-- :disabled="loading"
              :class="loading ? 'loading' : ''"
              :loading-text="loading ? 'Loading...' : 'Subscribe'"
              :error="error"
              :error-message="error" -->
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>

  <!-- footer section -->
  <div class="bg-white q-py-lg">
    <div class="container q-px-sm">
      <div class="row" :class="$q.screen.lt.sm ? 'text-center' : 'text-left'">
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
              Best information about the company gies here but now lorem ipsum
              is
            </p>
          </div>
          <ul
            class="flex q-gutter-x-sm no-padding q-my-md"
            :class="$q.screen.lt.sm ? 'flex-center' : 'items-center'"
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
                    clickable
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
      <div class="row justify-between items-center">
        <p class="fs-14 fw-light text-color-5 text-center no-margin">
          &copy; 2023 Ecommerce. All rights reserved.
        </p>
        <div>
          <q-select
            class="q-px-sm br-sm"
            style="min-width: 120px; border: 1px solid #8b96a5"
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
</template>

<script>
export default {
  data() {
    return {
      email: "",
      loading: false,
      error: null,
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
};
//
</script>

<style scoped>
.footer-items {
  transition: all 0.3s ease-in-out;
}
.footer-items:hover {
  padding-left: 20px;
  color: #0067ff;
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
</style>
