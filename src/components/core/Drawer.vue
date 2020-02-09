<template>
  <v-navigation-drawer
    id="app-drawer"
    v-model="inputValue"
    app
    dark
    floating
    persistent
    mobile-break-point="991"
    width="260"
  >
    <v-img
      src="https://demos.creative-tim.com/vue-material-dashboard/img/sidebar-2.32103624.jpg?__cf_chl_captcha_tk__=4b795e2b3559df3e722b2e64a4a3c7f641576ebf-1581237058-0-ASQ4-gGDEIwZmg1P2dCCH0EwTEZv_VSMBu-lqStsTKShQo_3LMbN5NbCWho2mGopxoU4z4TPGdGVJgbTYvX5JVOofF4kKOjVsGd5_KQs0CJBSoz4pkkqO7OLM_Xp3Mex_auva1XvMmckv9s27Nka8vfMYNPaTuEYQ_AXTph-_K8i1zc0AQizPfHKK_uTjFlOn2AprgltjINDZZt0TrkhMzdl4YbsXIxgy-Ws93cG1GBZI-TDkOfC8-4uRccdVhlIozz73gEjMEze6_5OSpLhcOWW9YgkdwxFzf2OEMIttP9KArmCkeNdWcQIKCpqBxz_h2LTDj7x72exYSl25E91NQJES7A9XSVoy5r2vz0-lPJPvxiR8fJrxGCbr4Oxzilnn0t3HYxXfsZnPQqSdoASbEQKjlh1v7Fw3DzMuP5Uo90D_WMUeOxMZNrfeFqkgeCxqg"
      height="100%"
    >
      <v-layout
        class="fill-height"
        tag="v-list"
        column
      >
        <v-list-tile avatar>
          <v-list-tile-avatar
            color="inherit"
          >
            <v-img
              :src="logo"
              height="34"
              contain
            />
          </v-list-tile-avatar>
          <v-list-tile-title class="title">
            IceGap
          </v-list-tile-title>
        </v-list-tile>
        <v-divider/>
        <v-list-tile
          v-for="(link, i) in links"
          :key="i"
          :to="link.to"
          active-class="blue"
          avatar
          class="v-list-item"
        >
          <v-list-tile-action>
            <v-icon>{{ link.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-title
            v-text="link.text"
          />
        </v-list-tile>
      </v-layout>
    </v-img>
  </v-navigation-drawer>
</template>

<script>
// Utilities
import {
  mapMutations,
  mapState
} from 'vuex'

export default {
  props: {
    opened: {
      type: Boolean,
      default: false
    }
  },
  data: () => ({
    logo: 'logo.png',
    links: [
      {
        to: '/',
        icon: 'mdi-view-dashboard',
        text: 'Dashboard'
      }
    ]
  }),
  computed: {
    ...mapState('app', ['image', 'color']),
    inputValue: {
      get () {
        return this.$store.state.app.drawer
      },
      set (val) {
        this.setDrawer(val)
      }
    },
    items () {
      return this.$t('Layout.View.items')
    }
  },

  methods: {
    ...mapMutations('app', ['setDrawer', 'toggleDrawer'])
  }
}
</script>

<style lang="scss">
  #app-drawer {
    .v-list__tile {
      border-radius: 4px;

      &--buy {
        margin-top: auto;
        margin-bottom: 17px;
      }
    }
  }
</style>
