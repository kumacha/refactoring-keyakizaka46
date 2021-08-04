<template>
  <v-app dark>
    <hamburger-menu />
    <GlobalNavigation />
    <v-main>
      <v-container>
        <keyakizaka-video :video-src="src" :video-type="type" />
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import KeyakizakaVideo from '~/components/Atoms/BackGroundVideo.vue';
import HamburgerMenu from '~/components/Molecules/HamburgerMenu.vue';
import GlobalNavigation from '~/components/Molecules/GlobalNavigation.vue';
export default {
  components: {
    KeyakizakaVideo,
    HamburgerMenu,
    GlobalNavigation,
  },
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      src: 'video/keyaki-backmovie.mp4',
      type: 'video/mp4',
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'keyakizaka46',
      arrays: [],
    };
  },
};
</script>
<style scoped>
.navi-btn {
  z-index: 1;
  right: 0;
}
</style>
