<template>
  <section class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-5 mx-2">
    <coupon-card
      v-for="couponCard in couponCards"
      :key="couponCard.couponId"
      :couponId="couponCard.couponId"
      :deal="couponCard.deal"
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
        { couponId: 'coupon1', deal: 50 },
        { couponId: 'coupon2', deal: 25 },
        { couponId: 'coupon3', deal: 100 },
      ],
    };
  },
};
</script>
