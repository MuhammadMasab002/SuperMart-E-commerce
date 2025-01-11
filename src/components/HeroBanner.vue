<template>
  <div class="container q-px-sm q-py-md">
    <div class="row justify-center items-center bg-white br-6 q-py-sm"
      :class=" $q.screen.lt.lg ? 'q-px-sm' : 'q-px-md'"
      style="border: 1px solid #DEE2E7">
      <div
        :class="$q.screen.lt.md ? 'hidden' : $q.screen.lt.lg ? 'col-3' : 'col visible'"
      >
        <q-list class="q-mr-md" dense>
          <q-item
            class="br-6 q-my-sm text-color-1"
            dense
            tag="a"
            v-ripple="false"
            v-for="(item, index) in LinkList"
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
                item.label
              }}</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </div>
      <div :class="$q.screen.gt.md ? 'col-7' : $q.screen.gt.md ? 'col-7' : 'col'">
        <div class="bg-banner q-py-xl text-color-2"
          :class="$q.screen.lt.md ? 'q-px-md' : 'q-px-xl'"
        >
          <div class="q-py-xl"
            :class="$q.screen.lt.sm ? 'q-my-none' : 'q-mb-xl q-mt-lg'"
          >
            <div class="fs-28 fw-light">Latest trending</div>
            <div class="fs-32 fw-semibold" style="line-height: 38px;">Electronic items</div>
            <div class="q-mt-sm">
              <q-btn label="Learn more" v-ripple="false" class="br-6 q-py-sm"  style="background-color: #fff; color: #0D6EFD; border: 1px solid #0D6EFD;" />
            </div>
          </div>
        </div>
      </div>
      <div class="col" :class="$q.screen.lt.lg ? 'hidden' : 'visible'">
        <div class="row q-pl-md q-gutter-y-sm">
          <div class="col-12">
            <div class="br-md bg-color-2 q-pa-md">
              <div class="flex justify-evenly items-center no-wrap">
                <q-avatar size="50px" >
                  <img
                    src="/images/icons/Avatar.png"
                    alt="User Avatar"
                  />
                </q-avatar>
                <p class="fs-18 fw-regular q-mb-none" style="line-height: 22px;">Hi, user <br :class="$q.screen.lt.lg ? 'hidden' : 'visible'"> let’s get stated</p>
              </div>
              <div class="q-gutter-y- q-mx-sm text-center">
                <q-btn label="Join now" v-ripple="false" class="br-6 q-mt-md no-shadow" style="width: 100%; background-color: #0D6EFD; color: #fff;" />
                <q-btn label="Log in" v-ripple="false" class="br-6 q-mt-sm"  style="width: 100%;  background-color: #fff; color: #0D6EFD; border: 1px solid #0D6EFD;" />
              </div>
            </div>
          </div>
          <div class="col-12">
            <div class="br-md bg-color-3 q-py-md q-px-lg text-white">
              <p class="fs-22 fw-light q-mb-none" style="line-height: 23px;">Get US $10 off <br> with a new <br> supplier</p>
            </div>
          </div>
          <div class="col-12">
            <div class="br-md bg-color-4 q-py-md q-px-lg text-white">
              <p class="fs-22 fw-light q-mb-none" style="line-height: 23px;">Send quotes with <br :class="$q.screen.lt.lg ? 'hidden' : 'visible'"> supplier <br> preferences</p>
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
      LinkList: [
        { label: "Automobiles", route: "/automobile" },
        { label: "Clothes and wear", route: "/clothes/wear" },
        { label: "Home interiors", route: "/homeInterior" },
        { label: "Computer and tech", route: "/tech" },
        { label: "Tools, equipment", route: "/toolsEquipment" },
        { label: "Sports and outdoor", route: "/sportOutdoor" },
        { label: "Animal and pets", route: "/AnimalPets" },
        { label: "Machinery tools", route: "/machineryTools" },
        { label: "More category", route: "/moreCategory" },
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
  content: '';
  background-image: url(/images/banners/Banner-board-800x420.png);
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
