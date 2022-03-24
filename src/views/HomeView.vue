<template>
  <div>
    <home-hero />
    <v-container class="popular-furniture">
      <v-row class="popular-furniture-row">
        <v-col cols="12">
          <section-title content="Mashhur mebellar" />
        </v-col>
        <v-col class="furniture" cols="12" sm="6" md="4" lg="3">
          <div class="link furniture-link">
            <img
              class="furniture-img"
              src="../assets/popular-furniture.png"
              alt="img"
            />
            <div class="furniture-info">
              <v-icon class="liked" @click="heart">mdi-heart</v-icon>
              <h3 class="furniture-cat">Category name</h3>
              <router-link to="#" class="link furniture-btn">View more</router-link>
            </div>
          </div>
        </v-col>
        <v-col class="furniture" cols="12" sm="6" md="4" lg="3">
          <div class="link furniture-link">
            <img
              class="furniture-img"
              src="../assets/popular-furniture.png"
              alt="img"
            />
            <div class="furniture-info">
              <v-icon class="liked" @click="heart">mdi-heart</v-icon>
              <h3 class="furniture-cat">Category name</h3>
              <router-link to="#" class="link furniture-btn">View more</router-link>
            </div>
          </div>
        </v-col>
        <v-col class="furniture" cols="12" sm="6" md="4" lg="3">
          <div class="link furniture-link">
            <img
              class="furniture-img"
              src="../assets/popular-furniture.png"
              alt="img"
            />
            <div class="furniture-info">
              <v-icon class="liked" @click="heart">mdi-heart</v-icon>
              <h3 class="furniture-cat">Category name</h3>
              <router-link to="#" class="link furniture-btn">View more</router-link>
            </div>
          </div>
        </v-col>
        <v-col class="furniture" cols="12" sm="6" md="4" lg="3">
          <div class="link furniture-link">
            <img
              class="furniture-img"
              src="../assets/popular-furniture.png"
              alt="img"
            />
            <div class="furniture-info">
              <v-icon class="liked" @click="heart">mdi-heart</v-icon>
              <h3 class="furniture-cat">Category name</h3>
              <router-link to="#" class="link furniture-btn">View more</router-link>
            </div>
          </div>
        </v-col>
        <v-col class="furniture" cols="12" sm="6" md="4" lg="3">
          <div class="link furniture-link">
            <img
              class="furniture-img"
              src="../assets/popular-furniture.png"
              alt="img"
            />
            <div class="furniture-info">
              <v-icon class="liked" @click="heart">mdi-heart</v-icon>
              <h3 class="furniture-cat">Category name</h3>
              <router-link to="#" class="link furniture-btn">View more</router-link>
            </div>
          </div>
        </v-col>
        <v-col class="furniture" cols="12" sm="6" md="4" lg="3">
          <div class="link furniture-link">
            <img
              class="furniture-img"
              src="../assets/popular-furniture.png"
              alt="img"
            />
            <div class="furniture-info">
              <v-icon class="liked" @click="heart">mdi-heart</v-icon>
              <h3 class="furniture-cat">Category name</h3>
              <router-link to="#" class="link furniture-btn">View more</router-link>
            </div>
          </div>
        </v-col>
        <v-col class="furniture" cols="12" sm="6" md="4" lg="3">
          <div class="link furniture-link">
            <img
              class="furniture-img"
              src="../assets/popular-furniture.png"
              alt="img"
            />
            <div class="furniture-info">
              <v-icon class="liked" @click="heart">mdi-heart</v-icon>
              <h3 class="furniture-cat">Category name</h3>
              <router-link to="#" class="link furniture-btn">View more</router-link>
            </div>
          </div>
        </v-col>
        <v-col class="furniture" cols="12" sm="6" md="4" lg="3">
          <div class="link furniture-link">
            <img
              class="furniture-img"
              src="../assets/popular-furniture.png"
              alt="img"
            />
            <div class="furniture-info">
              <v-icon class="liked" @click="heart">mdi-heart</v-icon>
              <h3 class="furniture-cat">Category name</h3>
              <router-link to="#" class="link furniture-btn">View more</router-link>
            </div>
          </div>
        </v-col>
        
      </v-row>
    </v-container>

    <v-container class="our-services">
      <v-row class="our-services-row">
        <v-col cols="12" class="our-services-col">
          <section-title content="Bizning xizmatlar"/>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import HomeHero from "@/components/HomeHero.vue";
import SectionTitle from "@/components/SectionTitle.vue";
export default {
  components: {
    HomeHero,
    SectionTitle,
  },
  data() {
    return {
      isclick: false
    }
  },
  methods: {
    heart(ev) {
      console.log(ev);
    }
  }
};
</script>
<style lang="scss" scoped>
.furniture-link {
  position: relative;
  display: block;
  margin-bottom: 100px;
  
  .furniture-info {
    // display: none;
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    z-index: 2;
    background: linear-gradient(0deg, rgba(24, 24, 24, 0.75), rgba(24, 24, 24, 0.75));
    transition: all 0.5s;
    opacity: 0;

    .liked {
      position: absolute;
      top: 10px;
      right: 10px;
      color: #fff;
    }
    .furniture-cat {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translateX(-50%) translateY(-50%);
      margin: 0;
      font-weight: 500;
      font-size: 16px;
      line-height: 19px;
      color: #FFFFFF;
    }
    .furniture-btn {
      position: absolute;
      margin: 0;
      bottom: 10px;
      left: 50%;
      transform: translateX(-50%);
      color: rgb(190, 170, 170);
    }
  }

  &:hover {
    .furniture-info {
      opacity: 1;
    }
  }
}
.furniture-img {
  position: relative;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 1;
}
</style>
