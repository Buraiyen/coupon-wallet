<template>
  <section class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5">
    <coupon-card />
    <coupon-card />
    <coupon-card />
    <coupon-card />
    <coupon-card />
  </section>
</template>

<script>
import couponCard from './coupon-card.vue';
export default {
  components: { couponCard },
};
</script>
