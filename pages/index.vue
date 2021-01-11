<template>
  <v-app>
    <v-main>
      <div>
        <v-img :src="require('../assets/Image 3-1.png')" style="opacity: 0.4">
          <h2 class="text-1">
            There is no grater agony than bearing an untold story inside you.
          </h2>
        </v-img>
      </div>
      <div v-for="info in infos" :key="info.id">
        <v-card class="mx-auto my-12" max-width="700">
          <template slot="progress">
            <v-progress-linear
              color="deep-purple"
              height="10"
              indeterminate
            ></v-progress-linear>
          </template>
          <v-card-title>
            <v-list-item>
              <v-list-item-avatar size="50"
                ><img alt="user" :src="require('../assets/pic.JPG')"
              /></v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title>{{ info.user_name }} </v-list-item-title>
                <v-list-item-subtitle>{{
                  info.timestamp
                }}</v-list-item-subtitle>
              </v-list-item-content>
              <v-spacer></v-spacer>
              <v-btn icon>
                <v-list-item-content>
                  <v-icon>mdi-dots-horizontal</v-icon>
                </v-list-item-content>
              </v-btn>
            </v-list-item>
          </v-card-title>
          <v-card-subtitle>{{ info.type }} </v-card-subtitle>

          <v-img height="208" :src="require('../assets/Image-3.png')">
            <div class="text-2">
              {{ info.post_content }}
            </div>
          </v-img>

          <v-card-text>
            <div>
              <v-card-actions>
                <div class="box">
                  <div class="logo_img" style="float: left"></div>
                  <div
                    style="
                      float: left;
                      color: red;
                      font: normal normal medium 12px/20px Sunflower, sans-serif;
                    "
                  >
                    {{ info.category }}
                  </div>
                </div>

                <div class="hashtag-1">
                  <span>#emotion</span>
                </div>

                <div class="hashtag-2">
                  <span>#memory</span>
                </div>
              </v-card-actions>
            </div>

            <div>
              <v-card-actions>
                <v-rating
                  :value="info.rating"
                  color="red"
                  length="1"
                  dense
                  half-increments
                  readonly
                  size="24"
                ></v-rating>
                <span>{{ info.rating }}</span>
                <span>({{ info.count }})</span>
                <v-spacer></v-spacer>
                <v-btn icon
                  ><v-icon>{{ info.comment_icon }}</v-icon></v-btn
                >
                <span>{{ info.no_of_comments }}</span>
                <v-spacer></v-spacer>
                <v-btn icon
                  ><v-icon>{{ info.share_icon }}</v-icon></v-btn
                >
                <v-spacer></v-spacer>
                <v-btn icon
                  ><v-icon>{{ info.bookmark_icon }}</v-icon></v-btn
                >
              </v-card-actions>
            </div>
          </v-card-text>
        </v-card>
      </div>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      infos: [
        {
          id: 1,
          user_name: 'chelsubhadeep',
          timestamp: '5 hours ago',
          type: 'Secret Confession',
          post_content:
            'Crestfallen then, buried within Breaking shackles, wistfully Longing For shimmer of charm on .',
          icon: '',
          category: 'Poeija',
          hashtags: ['emotions', 'memory'],
          rating: 4.6,
          count: 22,
          comment_icon: 'mdi-comment-text-outline',
          no_of_comments: 8,
          share_icon: 'mdi-share-variant',
          bookmark_icon: 'mdi-bookmark-outline',
        },
        {
          id: 2,
          user_name: 'chelsubhadeep',
          timestamp: '5 hrs ago',
          type: 'Secret Confession',
          post_content:
            'Crestfallen then, buried within Breaking shackles, wistfully Longing For shimmer of charm on .',
          icon: '',
          category: 'Poeija',
          hashtags: ['emotions', 'memory'],
          rating: 4.6,
          count: 22,
          comment_icon: 'mdi-comment-text-outline',
          no_of_comments: 8,
          share_icon: 'mdi-share-variant',
          bookmark_icon: 'mdi-bookmark-outline',
          decoration: 'logo_img',
        },
      ],
    }
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
        {
          rel: 'stylesheet',
          href:
            'https://fonts.googleapis.com/css?family=Kaushan+Script&display=swap',
        },
      ],
    }
  },
}
</script>
>
<style scoped>
.text-1 {
  top: 140px;
  left: 363px;
  width: 600px;
  height: 51px;
  text-align: left;
  font: normal normal normal 35px/40px Kaushan Script, sans-serif;
  letter-spacing: 0;
  color: #fff;
}
.text-2 {
  top: 534px;
  left: 353px;
  width: 660px;
  height: 86px;
  text-align: left;
  font: normal normal normal 25px/50px Kaushan Script, sans-serif;
  letter-spacing: 0%;
  color: #fbf4a8;
  opacity: 1;
}
.type-text {
  top: 705px;
  left: 384px;
  width: 31px;
  height: 12px;
  text-align: left;
  font: normal normal medium 12px/20px Sunflower, sans-serif;
  letter-spacing: 0%;
  color: #c93232;
  opacity: 1;
}
.box {
  top: 696px;
  left: 353px;
  width: 81px;
  height: 26px;
  background: #f1f1f1 0% 0% no-repeat padding-box;
  border-radius: 17px;
  opacity: 1;
}
.hashtag-1 {
  top: 696px;
  left: 444px;
  width: 73px;
  height: 26px;
  background: #f1f1f1 0% 0% no-repeat padding-box;
  border-radius: 17px;
  color: #c93232;
  opacity: 1;
}
.hashtag-2 {
  top: 696px;
  left: 528px;
  width: 73px;
  height: 26px;
  background: #f1f1f1 0% 0% no-repeat padding-box;
  border-radius: 17px;
  color: #c93232;
  opacity: 1;
}
.last-row {
  top: 747px;
  left: 353px;
  width: 660px;
  height: 24px;
  opacity: 1;
}
.post-content {
  top: 534px;
  left: 353px;
  width: 660px;
  height: 86px;
  text-align: left;

  /* font: normal normal normal 25px/50px Kaushan Script; */
  letter-spacing: 0%;
  color: #fbf4a8;
  opacity: 1;
}
.logo_img {
  top: 699px;
  left: 358px;
  width: 20px;
  height: 20px;
  background: transparent url('../assets/ic_poejia-1.png') 0% 0% no-repeat
    padding-box;
  opacity: 1;
}
</style>
