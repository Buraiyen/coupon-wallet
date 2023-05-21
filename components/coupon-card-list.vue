<template>
  <section
    class="grid justify-center grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-5 mx-2"
  >
    <coupon-card
      v-for="couponCard in couponCards"
      :key="couponCard.couponId"
      :couponId="couponCard.couponId"
      :deal="couponCard.deal"
      :colorTheme="couponCard.colorTheme"
      :code="couponCard.code"
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
        { couponId: 'coupon1', deal: 50, colorTheme: 'rose', code: '0AM9TKA' },
        { couponId: 'coupon2', deal: 25, colorTheme: 'sky', code: 'PME59N' },
        { couponId: 'coupon3', deal: 100, colorTheme: 'amber', code: 'B1VC32' },
      ],
    };
  },
};
</script>
