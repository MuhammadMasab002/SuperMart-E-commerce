<template>
  <div class="bg-color-1 q-py-lg q-px-sm">
    <div class="column q-py-lg">
      <div class="q-mb-sm text-center">
        <h4
          class="text-h4 text-color-2 fw-medium no-margin q-py-none"
          style="line-height: 28px"
        >
          Subscribe on our newsletter
        </h4>
        <p class="fs-16 fw-light text-color-5 q-my-sm">
          Get daily news on upcoming offers from many suppliers all over the
          world
        </p>
      </div>
      <div class="row flex-center">
        <form @submit.prevent="handleSubmit">
          <div class="flex justify-center">
            <div class="q-field">
              <q-input
                id="email"
                v-model="email"
                type="email"
                outlined
                bg-color="white"
                filled="true"
                dense
                class="q-px-sm br-6"
                placeholder="Enter your email address"
              >
                <template v-slot:prepend>
                  <q-icon name="mail" />
                </template>
              </q-input>
              <div v-if="error" class="q-my-sm text-negative fs-14 text-center">
                {{ error }}
              </div>
            </div>
            <div class="text-center q-py-s">
              <q-btn
                type="submit"
                dense
                :ripple="false"
                class="bg-color-gradient text-white q-px-md q-py-sm br-6"
                :loading="loading"
                loading-color="white"
              >
                Subscribe
              </q-btn>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>


</template>

<script>
export default {
  data() {
    return {
      email: "",
      loading: false,
      error: null,
    };
  },
  // :disabled="loading"
  // :class="loading ? 'loading' : ''"
  // :loading-text="loading ? 'Loading...' : 'Subscribe'"
  // :error="error"
  // :error-message="error"
  methods: {
    handleSubmit() {
      this.loading = true;
      this.error = null;

      setTimeout(() => {
        if (this.email.includes("@gmail.com")) {
          this.loading = false;
          alert("Thank you for your subscription!");
        } else {
          this.error = "Invalid email address.";
          this.loading = false;
        }
      }, 2000);
    },
  },
};
//
</script>

<style scoped>

</style>
