<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar>
        <template v-slot:prepend>
          <img class="ps-2" :height="30" src="/icon-192.png" />
          <div class="ps-2">AWS Game</div>
        </template>
        <v-spacer></v-spacer>

        <v-btn :icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'" slim
          @click="onClick">
        </v-btn>
      </v-app-bar>

      <v-navigation-drawer>
        <v-list>
          <v-list-item title="Navigation drawer"></v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-main>
        <v-container class="pa-0 h-100">
          <slot />
        </v-container>
      </v-main>
    </v-app>
  </v-responsive>
</template>

<script setup lang="ts">
const theme = useTheme()
function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>