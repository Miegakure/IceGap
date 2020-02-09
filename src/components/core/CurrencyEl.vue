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
      color="blue"
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
        TRX: 'TRON',
        BNB: 'Binance Coin',
        NEO: 'NEO',
        OKB: 'Okex',
        LINK: 'Chainlink',
        XTZ: 'Tezos',
        MANA: 'Decentraland',
        OGN: 'Origin Protocol',
        ZEC: 'ZCash',
        XMR: 'Monero',
        QTUM: 'QTUM',
        BTG: 'Bitcoin Gold',
        ADA: 'Cardano',
        ONT: 'Ontology',
        ICX: 'Icon Project',
        TRUE: 'True Chain',
        BCD: 'Bitcoin Diamond',
        XLM: 'Stellar'
      }
    }
  }
}
</script>
