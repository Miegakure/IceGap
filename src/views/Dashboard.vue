<template>
  <v-container
    fill-height
    fluid
    grid-list-xl
  >
    <v-layout wrap>
      <!-- eslint-disable -->
      <currency-el
        v-bind:cryptos="cryptos"
      />
    </v-layout>
  </v-container>
</template>

<script>
import axios from 'axios'
import CurrencyEl from '@/components/core/CurrencyEl.vue'

export default {
  components: {
    CurrencyEl
  },
  data () {
    return {
      cryptos: [],
      errs: []
    }
  },
  created () {
    axios.get('https://min-api.cryptocompare.com/data/pricemulti?fsyms=BTC,BSV,ETH,BCH,EOS,ETC,LTC,DASH,XRP,TRX,BNB,NEO,OKB,LINK,XTZ,MANA,OGN,ZEC,XMR,QTUM,BTG,ADA,ONT,ICX,TRUE,BCD,XLM&tsyms=USD,EUR')
      .then(responce => {
        this.cryptos = responce.data
      })
      .catch(error => this.errs.push(error))
  }
}
</script>
