<template>
  <div
    class="text-white rounded-lg border-rose-200 grid grid-cols-1 lg:grid-cols-3 xl:grid-cols-3"
  >
    <!-- "% off" section -->
    <div
      :class="[
        {
          'bg-rose-400': colorTheme === 'rose',
          'bg-sky-400': colorTheme === 'sky',
          'bg-amber-400': colorTheme === 'amber',
        },
        'flex',
        'items-center',
        'justify-center',
        'col-span-1',
        'max-lg:rounded-tl-lg',
        'max-lg:rounded-tr-lg',
        'lg:rounded-bl-lg',
        'lg:rounded-tl-lg',
      ]"
    >
      <font-awesome-icon :icon="['fas', 'gift']" size="xl" />
      <h3 class="text-6xl">{{ deal }}</h3>
      <div class="grid grid-rows-2">
        <p class="text-3xl">%</p>
        <p class="text-xl">OFF</p>
      </div>
    </div>

    <!-- Gift code section -->
    <div
      :class="[
        {
          'bg-rose-900': colorTheme === 'rose',
          'bg-sky-900': colorTheme === 'sky',
          'bg-amber-900': colorTheme === 'amber',
        },
        'col-span-2',
        'text-center',
        'max-lg:rounded-bl-lg',
        'max-lg:rounded-br-lg',
        'lg:rounded-tr-lg',
        'lg:rounded-br-lg',
      ]"
    >
      <div class="container mx-auto px-4 py-2">
        <div>
          <button
            :class="[
              {
                'text-rose-800 border-rose-300 hover:bg-rose-200':
                  colorTheme === 'rose',
                'text-sky-800 border-sky-300 hover:bg-sky-200 ':
                  colorTheme === 'sky',
                'text-amber-800 border-amber-300 hover:bg-amber-200':
                  colorTheme === 'amber',
                'bg-transparent text-gray-100 hover:bg-transparent': isRedeemed,

                'bg-gray-50': !isRedeemed,
              },
              'border-solid',
              'py-2',
              'w-[33%]',
              'transition-colors',
              'border-2',
              'rounded-md',
            ]"
            @click="redeem"
          >
            <span v-if="!isRedeemed">Redeem</span>
            <span v-else class="text-gray-50">{{ code }}</span>
          </button>
          <p v-show="isCopyMessageActive" class="text-gray-50 h-0">
            Copied to clipboard!
          </p>
        </div>

        <!-- Information section -->
        <div class="mt-6">
          <p class="font-bold">Lorem ipsum dolor, sit amet.</p>

          <!-- Phone -->
          <div class="font-bold mt-4">
            <span>
              <a
                href="tel:123-456-7890"
                :class="[
                  {
                    'hover:text-rose-300': colorTheme === 'rose',
                    'hover:text-sky-300': colorTheme === 'sky',
                    'hover:text-amber-300': colorTheme === 'amber',
                  },
                  'transition-colors',
                ]"
                >(123) 456-7890</a
              >
              <br />

              <!-- Email -->
              <a
                href="mailto:fake@example.com"
                :class="[
                  {
                    'hover:text-rose-300': colorTheme === 'rose',
                    'hover:text-sky-300': colorTheme === 'sky',
                    'hover:text-amber-300': colorTheme === 'amber',
                  },
                  'transition-colors',
                ]"
                >fake@example.com</a
              >
            </span>
            <br />

            <!-- Website -->
            <a
              href="#"
              :class="[
                {
                  'text-rose-300': colorTheme === 'rose',
                  'text-sky-300': colorTheme === 'sky',
                  'text-amber-300': colorTheme === 'amber',
                },
                'uppercase',
                'transition-colors',
                'hover:text-gray-50',
              ]"
              >fakewebsite.com</a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    couponId: {
      type: String,
      required: true,
    },
    deal: {
      type: Number,
      required: true,
    },
    colorTheme: {
      type: String,
      required: true,
      default: 'rose',
    },
    code: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      isRedeemed: sessionStorage[this.couponId] === 'true',
      isCopyMessageActive: false,
    };
  },
  methods: {
    redeem() {
      if (!this.isRedeemed) {
        this.isRedeemed = true;
        sessionStorage.setItem(this.couponId, 'true');
      }
      this.copyToClipboard();
    },
    copyToClipboard() {
      navigator.clipboard.writeText(this.code);
      this.isCopyMessageActive = true;
      setTimeout(() => {
        this.isCopyMessageActive = false;
      }, 3000);
    },
  },
};
</script>
