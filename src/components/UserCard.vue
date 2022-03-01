<template>
  <div
    :class="[
      'rounded-lg border border-gray-400 bg-white p-1.5',
      bg && 'bg-green-100',
    ]"
    @click="bg = !bg"
  >
    <div :class="['font-bold text-green-700']">{{ 行政區 }}</div>
    <div class="text-right">
      <a :href="`mailto:${email}`">{{ 設置位置 }}</a>
    </div>
  </div>
</template>

<script>
export default {
  props: ["id", "name", "email", "行政區", "設置位置"],
  data() {
    return {
      bg: false,
    };
  },
};
</script>

<style></style>
