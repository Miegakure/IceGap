<template>
  <v-footer
    id="core-footer"
    absolute
    height="82"
  >
    <span class="font-weight-light copyright">
      IceGap
      &copy;
      2019 -
      {{ (new Date()).getFullYear() }}
      Powered by Cryptocompare API
    </span>
  </v-footer>
</template>

<style>
#core-footer {
  z-index: 0;
}
</style>
