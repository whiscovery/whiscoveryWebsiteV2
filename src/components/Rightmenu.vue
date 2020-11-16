<template>
  <div class="div-menu" height="424">
    <v-sheet
      class="mx-auto"
      color="white"
      elevation="1"
      height="300"
      width="90%"
    >
      <v-system-bar></v-system-bar>
      <v-list>
        <v-list-item>
          <v-list-item-avatar>
            <v-img src="https://cdn.vuetifyjs.com/images/john.png"></v-img>
          </v-list-item-avatar>
        </v-list-item>

        <v-list-item link>
          <v-list-item-content>
            <v-list-item-title class="title">
              John Leider
            </v-list-item-title>
            <v-list-item-subtitle>john@vuetifyjs.com</v-list-item-subtitle>
          </v-list-item-content>

          <v-list-item-action>
            <v-icon>mdi-menu-down</v-icon>
          </v-list-item-action>
        </v-list-item>

        <v-divider></v-divider>
        <v-list-item-group v-model="selectedItem" color="primary">
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-folder</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>aaaaaaaaaaaaaaaaaa</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-sheet>
  </div>
</template>

<script>
export default {};
</script>
