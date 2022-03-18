<template>
  <header>
    <!-- header top  -->
    <v-container>
      <v-row align="center">
        <v-col cols="2">
          <router-link to="#">
            <img src="../assets/logo.png" alt="Bu yerda logo rasmi" />
          </router-link>
        </v-col>
        <v-col cols="4">
          <div class="search-wrapper">
            <input class="search" type="text" v-model="search" />
            <v-icon class="search-icon">mdi-magnify</v-icon>
          </div>
        </v-col>
        <v-col cols="2" class="">
          <div class="d-flex justify-space-around social-media">
            <router-link to="#" class="link">
              <v-icon>mdi-facebook</v-icon>
            </router-link>
            <router-link to="#" class="link">
              <v-icon>mdi-instagram</v-icon>
            </router-link>
            <router-link to="#" class="link">
              <v-icon>mdi-whatsapp</v-icon>
            </router-link>
          </div>
        </v-col>
        <v-col cols="2" class="text-left email-date">
          <p>
            <v-icon color="red">mdi-clock</v-icon>
            <span>Пн-Пт, 9:00 до 18:00</span>
          </p>
          <p>
            <v-icon color="red">mdi-email</v-icon>
            <span>zakaz@mir-kovrolina.ru</span>
          </p>
        </v-col>
        <v-col cols="2" class="registration text-right">
          <button class="register-btn" @click="dialog = true">
            <span>Ro'yhatdan o'tish</span>
          </button>
        </v-col>
      </v-row>
    </v-container>

    <!-- regiter modal  -->
    <v-row justify="center">
      <v-dialog
        v-model="dialog"
        scrollable
        persistent
        max-width="500px"
        transition="dialog-transition"
      >
        <v-card>
          <v-card-title class="justify-center">
            Registratsiyadan O'tish
          </v-card-title>
          <v-card-text>
            <v-text-field
              label="Email"
              prepend-icon="mdi-email"
              v-model="email"
              :rules="[() => !!email || 'This field is required']"
              :error-messages="errorMessages"
              required
            ></v-text-field>
            <v-text-field
              label="Password"
              :type="showPassword ? 'text' : 'password'"
              prepend-icon="mdi-lock"
              :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
              :rules="[rules.required, rules.min]"
              hint="At least 8 characters"
              @click:append="showPassword = !showPassword"
              v-model="parol"
            ></v-text-field>

            <v-text-field
              label="Check Password"
              :type="showPassword2 ? 'text' : 'password'"
              prepend-icon="mdi-lock"
              :append-icon="showPassword2 ? 'mdi-eye' : 'mdi-eye-off'"
              :rules="[rules.required, rules.min, rules.emailMatch]"
              hint="At least 8 characters"
              @click:append="showPassword2 = !showPassword2"
              v-model="checkParol"
            ></v-text-field>
          </v-card-text>
          <v-divider></v-divider>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="green darken-1" text @click="dialog = false">
              Disagree
            </v-btn>
            <v-btn color="green darken-1" text @click="dialog = false">
              Agree
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-row>

    <!-- header botttom  -->
    <v-divider class="mt-5 mb-3"></v-divider>
    <v-container>
      <v-row align="center">
        <v-col cols="11">
          <ul class="d-flex px-3 justify-space-between align-center nav_list">
            <li class="nav-link">
              <router-link class="link d-flex align-center" to="#">
                <v-icon class="mr-1" centered>mdi-menu</v-icon>
                Katalog
              </router-link>
            </li>
            <li class="nav-link">
              <router-link class="link" to="#">Xizmatlar</router-link>
            </li>
            <li class="nav-link">
              <router-link class="link" to="#">Galereya</router-link>
            </li>
            <li class="nav-link">
              <router-link class="link" to="#">Aksiya</router-link>
            </li>
            <li class="nav-link">
              <router-link class="link" to="#">Kompaniya haqida</router-link>
            </li>
            <li class="nav-link">
              <router-link class="link" to="#">Kontakt</router-link>
            </li>
            <li class="nav-link">
              <router-link class="link d-flex align-center" to="#">
                <v-icon class="mr-1">mdi-basket-plus</v-icon>
                Korzinka
              </router-link>
            </li>
          </ul>
        </v-col>
        <v-col cols="1">
          <v-select
            :items="languages"
            v-model="language"
          ></v-select>
        </v-col>
      </v-row>
    </v-container>
    <v-divider class="mt-3"></v-divider>
  </header>
</template>

<script>
export default {
  name: "SiteNav",

  data: () => ({
    search: "",
    dialog: false,
    email: "",
    parol: "",
    checkParol: "",
    errorMessages: "",
    showPassword: false,
    showPassword2: false,
    language: "Uz",
    languages: ['Uz', 'Eng', "Ru"]
  }),
  computed: {
    rules() {
      let parol = this.parol;
      return {
        required: (value) => !!value || "Required.",
        min: (v) => v.length >= 8 || "Min 8 characters",
        emailMatch: (value) =>
          value == parol || `the password you entered don't match`,
      };
    },
  },
};
</script>
<style lang="scss" scoped>
/* -------------------------------------------------------------------------- */
/*                                   HEADER                                   */
/* -------------------------------------------------------------------------- */
.search-wrapper {
  display: flex;
  padding: 8px 13px;
  border: 1px solid #a4a4a4;
  border-radius: 4px;

  input {
    flex-grow: 1;
    margin-right: 8px;
    outline: none;
    border-right: 1px solid #a4a4a4;
  }

  .search-icon {
    cursor: pointer;
    font-size: 24px;
  }
}
.email-date {
  p {
    margin: 0 !important;
    font-weight: 400;
    font-size: 12px;
    line-height: 14px;
    color: #181818;
    text-align: left;

    .v-icon {
      font-size: 15px;
      margin-right: 12px;
    }
  }
  p:last-child {
    margin-top: 5px !important;
  }
}
.register-btn {
  position: relative;
  padding: 10px;
  font-weight: 500;
  font-size: 14px;
  line-height: 16px;
  text-transform: uppercase;
  color: #181818;
  border: 2px solid #a4a4a4;
  border-radius: 4px;
  transition: all 0.5s;
  span {
    position: relative;
    z-index: 1;
  }
  &::before {
    width: 0%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    content: "";
    // z-index: -1;
    background-color: #cc0000;
    transition: all 0.3s;
  }
  &:hover {
    color: #fff;
    border-color: #cc0000;
  }
  &:hover:before {
    width: 100%;
  }
}

/* -------------------------------------------------------------------------- */
/*                                  site nav                                  */
/* -------------------------------------------------------------------------- */

.nav_list {
  margin: 0;
  padding: 0;
  list-style-type: none;
}
.nav-link {
  .link {
    display: block;
    position: relative;
    padding-top: 10px;
    padding-bottom: 10px;
    font-weight: 500;
    font-size: 16px;
    line-height: 19px;
    color: #181818;

    &::before {
      position: absolute;
      top: 100%;
      width: 100%;
      left: 0;
      content: "";
      opacity: 0;
      background: #a4a4a4;
      transition: height 0.3s, opacity 0.3s, transform 0.3s;
      transform: translateY(-8px);
    }
    &:hover::before {
      height: 2px;
      opacity: 1;
      transform: translateY(0);
    }
  }
}
</style>