<template>
  <div
    class="w-[30%] max-lg:w-[50%] text-white rounded-lg border-rose-200 grid grid-cols-1 lg:grid-cols-3 xl:grid-cols-3"
  >
    <div
      class="bg-rose-400 flex items-center justify-center col-span-1 max-lg:rounded-tl-lg max-lg:rounded-tr-lg lg:rounded-bl-lg lg:rounded-tl-lg"
    >
      <div>
        <font-awesome-icon :icon="['fas', 'gift']" size="xl" />
      </div>
      <h3 class="text-6xl">30</h3>
      <div class="grid grid-rows-2">
        <p class="text-3xl">%</p>
        <p class="text-xl">OFF</p>
      </div>
    </div>
    <div
      class="bg-rose-900 col-span-2 text-center max-lg:rounded-bl-lg max-lg:rounded-br-lg lg:rounded-tr-lg lg:rounded-br-lg"
    >
      <div class="container mx-auto px-4 py-2">
        <!-- Gift code section -->
        <div>
          <p class="uppercase font-bold">Your promo code:</p>
          <p
            class="uppercase border-solid font-bold border-2 border-rose-600 py-3 text-2xl rounded-lg text-rose-200"
          >
            Giftcode
          </p>
        </div>

        <!-- Information section -->
        <div class="mt-4">
          <p class="font-bold">Lorem ipsum dolor, sit amet.</p>
          <div class="font-bold mt-4">
            <span>
              <a
                href="tel:123-456-7890"
                class="transition-colors hover:text-rose-300"
                >(123) 456-7890</a
              >
              <br />
              <a
                href="mailto:fake@example.com"
                class="transition-colors hover:text-rose-300"
                >fake@example.com</a
              >
            </span>
            <br />
            <a
              href="#"
              class="uppercase text-rose-300 transition-colors hover:text-gray-50"
              >fakewebsite.com</a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style></style>
