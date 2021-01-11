<template>
  <v-app>
    <v-main>
      <v-toolbar class="toolbars">
        <img
          class="logo"
          :src="require('../assets/jiya-logo.png')"
          height="40"
        />

        <v-toolbar-title>
          <n-link to="/"
            ><span
              style="
                top: 29px;
                left: 120px;
                width: 50px;
                height: 27px;
                text-align: center;
                letter-spacing: 0%;
                color: #222;
                opacity: 1;
                font: normal normal bold 22px/27px Montserrat, sans-serif;
              "
              >JIYA</span
            ></n-link
          >
        </v-toolbar-title>

        <v-spacer></v-spacer>

        <v-flex>
          <v-form>
            <v-text-field
              class="search-box"
              label="Search"
              prepend-inner-icon="mdi-magnify"
              solo
            >
            </v-text-field>
          </v-form>
        </v-flex>
        <v-spacer></v-spacer>
        <v-app-bar-nav-icon><v-icon>mdi-bell</v-icon></v-app-bar-nav-icon>
        <v-spacer></v-spacer>
        <v-list-item-avatar>
          <img class="logo" :src="require('../assets/pic.jpg')" height="40" />
        </v-list-item-avatar>
        <v-toolbar-items class="hidden-sm-and-down">
          <v-btn text><n-link to="/">chel_subhadeep</n-link></v-btn>
        </v-toolbar-items>

        <v-btn icon>
          <v-icon>mdi-chevron-down</v-icon>
        </v-btn>
      </v-toolbar>

      <div class="left-bar">
        <v-list width="300">
          <v-list-item-group color="red">
            <v-list-item
              v-for="item in items"
              :key="item.title"
              :to="item.to"
              link
              router
              exact
            >
              <v-list-item-icon>
                <v-icon>{{ item.icon }}</v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </div>
      <div class="right-bar">
        <nuxt />
      </div>
    </v-main>

    <v-footer class="downbar">
      <span class="first_text">{{ copyright }}</span>
      <v-spacer></v-spacer>
      <v-spacer></v-spacer>
      <v-spacer></v-spacer>
      <v-spacer></v-spacer>
      <v-spacer></v-spacer>
      <v-spacer></v-spacer>
      <span class="other_texts">Contact</span>
      <v-spacer></v-spacer>
      <span class="other_texts">|</span>
      <v-spacer></v-spacer>
      <span class="other_texts">Terms & Conditions</span>
      <v-spacer></v-spacer>
      <span class="other_texts">|</span>
      <v-spacer></v-spacer>
      <span class="other_texts">Privacy Policy</span>
      <v-spacer></v-spacer>
    </v-footer>
  </v-app>
</template>

<script>
// import '@fontsource/sunflower'
export default {
  data() {
    const date = new Date()
    const year = date.getFullYear()
    return {
      items: [
        { title: 'Home', icon: 'mdi-home', to: '/' },
        { title: 'Explore', icon: 'mdi-compass', to: '/explore' },
        { title: 'Leaderboard', icon: 'mdi-chart-bar' },
        { title: 'Draft', icon: 'mdi-email-open', to: '/draft' },
        { title: 'Bookmark', icon: 'mdi-bookmark', to: '/bookmark' },
      ],
      right: null,
      copyright: 'Copyright@' + year + 'All Rights Reverved.',
      footer_info: ['Contact', 'Terms & Conditions', 'Privacy Policy'],
    }
  },

  computed: {
    icon() {
      return `http://localhost:3000/_nuxt/icons/icon_64x64.5f6a36.png`
    },
  },
  head() {
    return {
      script: [
        {
          src:
            'https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js',
        },
      ],
      link: [
        {
          rel: 'stylesheet',
          href: 'https://fonts.googleapis.com/css?family=Roboto&display=swap',
        },
      ],
    }
  },
}
</script>

<style scoped>
a {
  text-decoration: none;
  color: black;
  text-transform: none;
}
h1 {
  color: white;
}
#center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 10%;
}

.left-bar {
  float: left;
}
.right-bar {
  float: left;
  top: 110px;
  left: 333px;
  width: 700px;
  height: 248px;

  /* width: 66.66%; */
  padding: 50px;

  /* opacity: 0.4; */
}
.cover-image {
  top: 110px;
  left: 333px;
  width: 700px;
  height: 248px;
  background: #000 0% 0% no-repeat padding-box;
  border-radius: 3px;
  opacity: 0.4;
}

.home-icon {
  top: 111px;
  left: 50px;
  width: 19px;
  height: 18px;
  background: transparent url('../assets/home.png') 0% 0% no-repeat padding-box;
  opacity: 1;
}
.home-font {
  top: 109px;
  left: 83px;
  width: 40px;
  height: 20px;
  text-align: left;

  /* font: normal normal normal 16px/30px Source Sans Pro; */
  letter-spacing: 0%;
  color: #d32f2f;
  opacity: 1;
}
.logo {
  top: 16px;
  left: 50px;
  width: 50px;
  height: 52px;
  opacity: 1;
}
.toolbars {
  top: 0%;
  left: 0%;
  width: 1366px;
  height: 80px;
  background: #fff 0% 0% no-repeat padding-box;
  box-shadow: 0% 3px 6px #d32f2f29;
  opacity: 1;
}
.search-box {
  top: 18px;
  left: 333px;
  width: 700px;
  height: 48px;
  background: #fff 0% 0% no-repeat padding-box;
  border: 1px solid #d5d5d5;
  border-radius: 3px;
  opacity: 1;
}
.title {
  top: 29px;
  left: 120px;
  width: 50px;
  height: 27px;
  text-align: center;
  letter-spacing: 0%;
  color: #222;
  opacity: 1;
}
.first_text {
  /* top: 2162px;
  left: 815px;
  width: 500px;
  height: 16px; */
  text-align: left;

  /* font: normal normal medium 16px/30px Sunflower; */
  letter-spacing: 0%;
  color: #8a7579;
  opacity: 1;
}
.other_texts {
  /* top: 2162px;
  left: 815px;
  width: 500px;
  height: 16px; */
  text-align: center;

  /* font: normal normal medium 16px/30px Montserrat; */
  letter-spacing: 0%;
  color: #8a7579;
  opacity: 1;
}
.downbar {
  top: 2130px;
  color: white;
  left: 0%;
  width: 1366px;
  height: 76px;
  background: #2b000a 0% 0% no-repeat padding-box;
  opacity: 1;
}
.last-icon {
  top: 39px;
  left: 1308px;
  width: 9px;
  height: 4px;
  border: 2px solid var(--unnamed-color-33322d);
  border: 2px solid #33322d;
  opacity: 1;
}

.cover-text {
  top: 140px;
  left: 363px;
  width: 600px;
  height: 51px;
  text-align: left;

  /* font: normal normal normal 35px/40px Kaushan Script; */
  letter-spacing: 0%;
  color: #fff;
  opacity: 1;
}
.cover-writer {
  top: 211px;
  left: 363px;
  width: 124px;
  height: 23px;
  text-align: left;

  /* font: normal normal medium 16px/40px Sunflower; */
  letter-spacing: 0%;
  color: #fff;
  opacity: 1;
}
</style>
