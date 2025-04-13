<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar>
        <template v-slot:prepend>
          <NuxtLink to="/" class="d-flex align-center text-decoration-none">
            <img class="ps-2" :height="30" src="/icon-192.png" />
            <div class="ps-2 text-white">AWS Game</div>
          </NuxtLink>
        </template>
        <v-spacer></v-spacer>
        <v-btn variant="text" to="/about" nuxt>
          About
        </v-btn>
        <v-btn :icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'" slim @click="onClick" />
      </v-app-bar>

      <v-navigation-drawer>
        <v-expansion-panels variant="accordion">
          <v-expansion-panel title="Tutorials">
            <v-expansion-panel-text>
              <v-list>
                <v-btn variant="text" to="/tutorials/handle-access" nuxt>
                  Access handling
                </v-btn>
              </v-list>
            </v-expansion-panel-text>
          </v-expansion-panel>
          <v-expansion-panel title="Associate level">
          </v-expansion-panel>
          <v-expansion-panel title="Professional level">
          </v-expansion-panel>
        </v-expansion-panels>

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