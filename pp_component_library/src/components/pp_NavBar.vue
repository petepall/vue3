<template>
  <nav
    :class="{ scrolled: !view.atTopOfPage }"
    class="fixed flex w-full bg-blue-500 text-yellow-400 text-2xl text-center border-b items-center justify-between flex-wrap p-5 m-auto top-0 animated"
  >
    This is the header
  </nav>
</template>

<script>
import { ref, onBeforeMount } from 'vue';

export default {
  setup() {
    const view = ref({
      atTopOfPage: true,
    });

    onBeforeMount(() => {
      window.addEventListener('scroll', handleScroll);
    });

    function handleScroll() {
      if (window.pageYOffset > 0) {
        if (view.value.atTopOfPage) view.value.atTopOfPage = false;
      } else {
        if (!view.value.atTopOfPage) view.value.atTopOfPage = true;
      }
    }

    return {
      view,
    };
  },
};
</script>

<style lang="scss" scoped>
nav {
  z-index: 10;
}

nav.scrolled {
  @apply shadow-2xl;
  border-bottom: 0px;
}
</style>
