<template>
  <q-layout view="lHh Lpr lFf">
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
                <q-img width="150px" height="auto" src="/images/logo/logo-colored.png"></q-img>
              </div>
            </div>
            <div
              class="br-md flex bg-white"
              :class="$q.screen.lt.md ? 'hidden' : 'visible'"
              style="border: 2px solid #0d6efd"
            >
              <q-input
                class="br-md q-px-sm"
                style="min-width: 250px"
                borderless
                square
                v-model="text"
                dense
                placeholder="Search"
                clearable
              />
              <div>
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
                  v-model="selected"
                  :options="options"
                  label="All Categories"
                  transition-show="jump-up"
                  transition-hide="jump-up"
                />
              </div>
              <q-btn
                class="br-right"
                unelevated
                color="primary"
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
                <q-item class="no-padding" clickable>
                  <q-item-section>
                    <q-avatar square size="44px">
                      <q-icon name="person" color="grey" />
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
                  class="no-padding"
                  clickable
                  :class="$q.screen.gt.xs ? 'visible' : 'hidden'"
                >
                  <q-item-section>
                    <q-avatar square size="44px">
                      <q-icon name="message" color="grey" />
                      <q-item-label class="fs-10 fw-light"
                        >Message</q-item-label
                      >
                    </q-avatar>
                  </q-item-section>
                </q-item>
                <q-item
                  class="no-padding"
                  clickable
                  :class="$q.screen.gt.xs ? 'visible' : 'hidden'"
                >
                  <q-item-section>
                    <q-avatar square size="44px">
                      <q-icon name="favorite" color="grey" />
                      <q-item-label class="fs-10 fw-light">Orders</q-item-label>
                    </q-avatar>
                  </q-item-section>
                </q-item>
                <q-item class="no-padding" clickable>
                  <q-item-section>
                    <q-avatar square size="44px">
                      <q-icon name="shopping_cart" color="grey" />
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
                <q-item class="no-padding q-mx-xs" clickable>
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular q-px-sm"
                      >All category</q-item-label
                    >
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-xs" clickable>
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular q-px-sm"
                      >Hot offers</q-item-label
                    >
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-xs" clickable>
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular q-px-sm"
                      >Gift boxes</q-item-label
                    >
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-xs" clickable>
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular q-px-sm"
                      >Projects</q-item-label
                    >
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-xs" clickable>
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular q-px-sm"
                      >Menu item</q-item-label
                    >
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-sm" clickabl>
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular">
                      <q-select
                        class="q-px-sm br-sm"
                        style="min-width: 120px; border: 1px solid #8b96a5"
                        square
                        dense
                        borderless
                        v-model="selected"
                        :options="options"
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
                        class="q-px-sm br-sm"
                        style="min-width: 140px; border: 1px solid #8b96a5"
                        square
                        dense
                        borderless
                        v-model="selected"
                        :options="options"
                        label="English, USD"
                        transition-show="jump-up"
                        transition-hide="jump-up"
                      />
                    </q-item-label>
                  </q-item-section>
                </q-item>
                <q-item class="no-padding q-mx-md" clickabl>
                  <q-item-section>
                    <q-item-label class="fs-16 fw-regular">
                      <q-select
                        class="q-px-sm br-sm"
                        style="min-width: 120px; border: 1px solid #8b96a5"
                        square
                        dense
                        borderless
                        v-model="selected"
                        :options="options"
                        label="Ship to"
                        transition-show="jump-up"
                        transition-hide="jump-up"
                      >
                        <template v-slot:append>
                          <q-avatar square>
                            <q-img src="/images/flags/icon.png" />
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
                  :class="$q.screen.lt.sm ? 'br-6 custom-input' : 'br-left'"
                  style="border: 2px solid #0d6efd"
                  borderless
                  square
                  v-model="text"
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
                    v-model="selected"
                    :options="options"
                    label="All Categories"
                    transition-show="jump-up"
                    transition-hide="jump-up"
                  />
                  <q-btn
                    class="br-right"
                    unelevated
                    color="primary"
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

    <!-- <q-drawer v-model="leftDrawerOpen" bordered>
      <q-list>
        <q-item-label header> Essential Links </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer> -->

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
//import { ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";

export default {
  data() {
    return {
      leftDrawerOpen: false,

      text: "", // Added for q-input
      selected: null,
      options: ["Google", "Facebook", "Twitter", "Apple", "Oracle"],
      linksList: [
        {
          title: "Docs",
          caption: "quasar.dev",
          icon: "school",
          link: "https://quasar.dev",
        },
        {
          title: "Github",
          caption: "github.com/quasarframework",
          icon: "code",
          link: "https://github.com/quasarframework",
        },
        {
          title: "Discord Chat Channel",
          caption: "chat.quasar.dev",
          icon: "chat",
          link: "https://chat.quasar.dev",
        },
        {
          title: "Forum",
          caption: "forum.quasar.dev",
          icon: "record_voice_over",
          link: "https://forum.quasar.dev",
        },
        {
          title: "Twitter",
          caption: "@quasarframework",
          icon: "rss_feed",
          link: "https://twitter.quasar.dev",
        },
        {
          title: "Facebook",
          caption: "@QuasarFramework",
          icon: "public",
          link: "https://facebook.quasar.dev",
        },
        {
          title: "Quasar Awesome",
          caption: "Community Quasar projects",
          icon: "favorite",
          link: "https://awesome.quasar.dev",
        },
      ],
    };
  },
  methods: {
    toggleLeftDrawer() {
      this.leftDrawerOpen = !this.leftDrawerOpen;
    },
  },
};
</script>

<style>
.custom-input {
  width: 100%;
}
</style>
