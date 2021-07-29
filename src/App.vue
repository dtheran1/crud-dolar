<template>
  <v-app>
    <v-main>
      <v-container>
        <router-view />
        <v-dialog v-model="loading.estado" hide-overlay persistent width="300">
          <v-card :color="loading.color" dark>
            <v-card-text>
              <p class="text-xs-center">
                {{ loading.titulo }}
              </p>
              <v-progress-linear
                indeterminate
                color="white"
                class="mb-0"
              ></v-progress-linear>
            </v-card-text>
          </v-card>
        </v-dialog>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import { mapState } from "vuex";

export default {
  name: "App",

  data: () => ({
    //
  }),
  computed: {
    ...mapState(["loading"]),
  },
};
</script>
