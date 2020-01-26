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
      x Cryptocompare API x Vuetify Material Dashboard
    </span>
  </v-footer>
</template>

<style>
#core-footer {
  z-index: 0;
}
</style>
