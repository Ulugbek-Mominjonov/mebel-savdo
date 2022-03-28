
<template>
  <div class="katalog-section">
    <v-container class="katalog-container">
      <v-row class="katalog-row">
        <!-- katalog link  -->
        <v-col class="katalog-link" cols="3">
          <v-list dense>
            <v-list-item-group v-model="selectedItem" color="red">
              <v-list-item @click="changeMenu('Barcha bolimlar')">
                <v-list-item-content>
                  <v-list-item-title class="text-subtitle-1"
                    >Barcha bo'limlar
                  </v-list-item-title>
                </v-list-item-content>
                <v-list-item-icon>
                  <v-icon>mdi-chevron-right</v-icon>
                </v-list-item-icon>
              </v-list-item>

              <v-divider></v-divider>

              <v-list-item v-for="(item, i) in items" :key="i" @click="changeMenu(item.text)">
                <v-list-item-content>
                  <v-list-item-title v-text="item.text"></v-list-item-title>
                </v-list-item-content>
                <v-list-item-icon>
                  <v-icon v-text="item.icon"></v-icon>
                </v-list-item-icon>
              </v-list-item>
            </v-list-item-group>
          </v-list>
        </v-col>

        <!-- katalog content  -->
        <v-col class="katalog-content" cols="9">
          <v-row class="content-row">
            <v-col class="content-path" cols="12">
              <p class="content-name">Barcha bo'limlar</p>
              <div class="content-parent-path">
                <span>Bo'limlar ro'yhati</span>
                <v-icon size="18">mdi-chevron-right</v-icon>
              </div>
              <div class="content-current-path">
                <span>{{ pathName }}</span>
                <v-icon size="18" color="red">mdi-chevron-right</v-icon>
              </div>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedItem: 0,
      items: [
        { text: "Ofis uchun", icon: "mdi-chevron-right" },
        { text: "Uy uchun", icon: "mdi-chevron-right" },
        { text: "O'quv uchun", icon: "mdi-chevron-right" },
        { text: "Mehmonhona uchun", icon: "mdi-chevron-right" },
      ],
      pathName: "Barcha bo'limlar"
    };
  },
  methods: {
    changeMenu(value) {
      this.pathName = value
    }
  }
};
</script>

<style lang="scss" scoped>
.katalog-link {
  display: flex;
  flex-direction: column;
  border: 1px solid #e5e5e5;
}

/* -------------------------------------------------------------------------- */
/*                               katalog content                              */
/* -------------------------------------------------------------------------- */
.content-path {
  display: flex;
  align-items: flex-end;
}
.content-name::after {
  display: block;
  content: "";
  width: 10%;
  height: 1.5px;
  background-color: #bdb7b7;
}
.content-name {
  margin: 0;
  margin-right: 30px;
  font-weight: 400;
  font-size: 26px;
  line-height: 30px;
  color: #181818;
}
.content-parent-path {
  margin-right: 30px;
  span {
    font-size: 12px;
    font-weight: 400;
    line-height: 14px;
    color: #a4a4a4;
  }
}
.content-current-path {
  color: #cc0000;
  span {
    font-weight: 400;
    font-size: 12px;
    line-height: 14px;
  }
}
</style>
