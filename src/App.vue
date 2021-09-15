<template>
  <v-app>
    <v-main>
      <router-view/>
    </v-main>
    <v-footer style="background-color: green;">
      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>ООО БРАВЛСУПЕРУЛЬТРАМЕГАБОКСВЫБИВАНИЕЮТУБТВИЧВЗЛОМЧИТЫ</strong>
      </v-card-text>
    </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>
