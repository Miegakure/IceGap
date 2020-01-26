<template>
  <v-flex
    xl10
    lg10
    offset-xl1
    offset-lg1
  >
    <material-stats-card
      v-for="(price, cur) in cryptos"
      :key="cur"
      :title="cur"
      :value="'$' + String(price.USD) + ' | €' + String(price.EUR)"
      :sub-text="crs[cur]+' USD | EUR'"
      color="inherit"
    />
  </v-flex>
</template>

<script>
export default {
  props: {
    cryptos: {
      type: Object,
      default: null
    }
  },
  data () {
    return {
      crs: {
        BTC: 'Bitcoin',
        BSV: 'Bitcoin SV',
        ETH: 'Ethereum',
        BCH: 'Bitcoin Cash',
        EOS: 'EOS',
        ETC: 'Ethereum Classic',
        LTC: 'Litecoin',
        DASH: 'Dash',
        XRP: 'XRP',
        TRX: 'TRON'
      }
    }
  }
}
</script>
