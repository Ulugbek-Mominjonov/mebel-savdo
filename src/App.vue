<template>
  <v-app>
    <site-nav />
    <v-main>
      <router-view />
    </v-main>
    <site-footer />
  </v-app>
</template>

<script>
import SiteNav from '@/components/SiteNav.vue';
import SiteFooter from '@/components/SiteFooter.vue';
export default {
  name: "App",
  components: {
    SiteNav,
    SiteFooter
  },

  data: () => ({
    search: '',
  }),
};
</script>
<style lang="scss">
/* -------------------------------------------------------------------------- */
/*                                    FONTS                                   */
/* -------------------------------------------------------------------------- */
/* roboto-regular - latin */
@font-face {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  src: url('./fonts/roboto-v29-latin-regular.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
       url('./fonts/roboto-v29-latin-regular.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
}
/* roboto-500 - latin */
@font-face {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 500;
  src: url('./fonts/roboto-v29-latin-500.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
       url('./fonts/roboto-v29-latin-500.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
}
/* roboto-700 - latin */
@font-face {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 700;
  src: url('./fonts/roboto-v29-latin-700.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
       url('./fonts/roboto-v29-latin-700.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
}
/* roboto-900 - latin */
@font-face {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 900;
  src: url('./fonts/roboto-v29-latin-900.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
       url('./fonts/roboto-v29-latin-900.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
}

/* -------------------------------------------------------------------------- */
/*                                GENERAL STYLE                               */
/* -------------------------------------------------------------------------- */
body {
  margin: 0;
  padding: 0;
  font-family: "Roboto", "Arial", sans-serif;
}
.container {
  padding-top: 0 !important;
  padding-bottom: 0 !important;
}
.link {
  text-decoration: none;
}
.list-unstyle {
  display: flex;
  align-items: center;
  list-style-type: none;
  margin: 0;
  padding: 0;
}
img {
  display: block;
}
.link {
  display: block;
}
footer {
  display: none;
}
.v-navigation-drawer__content {
  padding: 20px;
}
</style>
