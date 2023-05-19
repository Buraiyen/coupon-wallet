<template>
  <section class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5 mx-2">
    <coupon-card
      v-for="couponCard in couponCards"
      :key="couponCard.couponId"
      :couponId="couponCard.couponId"
    />
  </section>
</template>

<script>
import couponCard from './coupon-card.vue';
export default {
  components: { couponCard },
  data() {
    return {
      couponCards: [
        { couponId: 'coupon1' },
        { couponId: 'coupon2' },
        { couponId: 'coupon3' },
      ],
    };
  },
};
</script>
