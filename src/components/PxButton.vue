<template>
  <button
    @click="buttonClick"
    class="w-100 bg-transparent hover:bg-green-500 focus:outline-none text-green-700 font-semibold hover:text-white py-2 px-2 border border-green-500 hover:boder-transparent rounded"
  >
    <beat-loader
      class="w-100"
      :loading="isLoading"
      :color="'#68d391'"
      :size="8"
    />
    <p v-show="!isLoading">
      <slot></slot>
    </p>
  </button>
</template>

<script>
export default {
  name: "PxButton",

  props: {
    isLoading: {
      type: Boolean,
      default: false
    }
  },

  methods: {
    buttonClick() {
      this.$emit("custom-click");
    }
  }
};
</script>
