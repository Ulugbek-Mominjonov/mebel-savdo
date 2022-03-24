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
              <router-link to="#" class="link furniture-btn"
                >View more</router-link
              >
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
              <router-link to="#" class="link furniture-btn"
                >View more</router-link
              >
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
              <router-link to="#" class="link furniture-btn"
                >View more</router-link
              >
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
              <router-link to="#" class="link furniture-btn"
                >View more</router-link
              >
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
              <router-link to="#" class="link furniture-btn"
                >View more</router-link
              >
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
              <router-link to="#" class="link furniture-btn"
                >View more</router-link
              >
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
              <router-link to="#" class="link furniture-btn"
                >View more</router-link
              >
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
              <router-link to="#" class="link furniture-btn"
                >View more</router-link
              >
            </div>
          </div>
        </v-col>
      </v-row>
    </v-container>

    <!-- Our services  -->
    <v-container class="our-services">
      <v-row class="our-services-row">
        <v-col cols="12" class="our-services-col">
          <section-title content="Bizning xizmatlar" />
        </v-col>

        <v-col
          cols="3"
          class="service"
          v-for="(item, index) in services"
          :key="index"
        >
          <div class="service-wrapper" @click="isclick = index">
            <img
              src="../assets/popular-furniture.png"
              alt="img"
              class="service-img"
              :class="{ 'service-img-click': isclick == index }"
            />
            <h4 class="services-name">{{ item }}</h4>
          </div>
        </v-col>
      </v-row>
    </v-container>

    <!-- friends  -->
    <v-container class="our-friends mb-15">
      <v-row class="friends-row">
        <v-col cols="12">
          <section-title content="Tanlashda yordam beramiz" />
        </v-col>
        <v-col class="friend" cols="12">
          <v-sheet class="mx-auto" elevation="8" max-width="auto">
            <v-slide-group
              v-model="model"
              class="pa-4"
              active-class="success"
              show-arrows
            >
              <v-slide-item
                v-for="n in 15"
                :key="n"
              >
                <img src="../assets/friend.png" alt="img">
              </v-slide-item>
            </v-slide-group>
          </v-sheet>
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
      isclick: -1,
      services: [
        "O'rnatib beramiz",
        "Yetkazib beramiz",
        "Xizmat nomi",
        "Xizmat nomi",
      ],
      model: null
    };
  },
  methods: {
    heart(ev) {
      console.log(ev);
    },
  },
};
</script>
<style lang="scss" scoped>
/* -------------------------------------------------------------------------- */
/*                              POPULAR FURNITURE                             */
/* -------------------------------------------------------------------------- */
.popular-furniture {
  margin-bottom: 100px;
}
.furniture-link {
  position: relative;
  display: block;

  .furniture-info {
    // display: none;
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    z-index: 2;
    background: linear-gradient(
      0deg,
      rgba(24, 24, 24, 0.75),
      rgba(24, 24, 24, 0.75)
    );
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
      color: #ffffff;
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
.furniture-img,
.service-img {
  position: relative;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 1;
}

/* -------------------------------------------------------------------------- */
/*                                OUR SERVICES                                */
/* -------------------------------------------------------------------------- */
.our-services {
  margin-bottom: 100px;
}
.service-wrapper {
  position: relative;
  cursor: pointer;

  .service-img {
    transition: all 0.3s;
  }
  .service-img-click {
    // transform: scale(1.2);
    // z-index: 3;
  }
  &::before {
    position: absolute;
    content: "";
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    background: linear-gradient(
      0deg,
      rgba(24, 24, 24, 0.75),
      rgba(24, 24, 24, 0.75)
    );
    opacity: 1;
    z-index: 2;
    transition: opacity 0.3s;
  }

  .services-name {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    z-index: 2;
    font-weight: 500;
    font-size: 16px;
    line-height: 19px;
    color: #ffffff;
    opacity: 1;
    transition: opacity 0.3s;
  }

  &:hover {
    &::before,
    .services-name {
      opacity: 0;
    }
  }
}


</style>
