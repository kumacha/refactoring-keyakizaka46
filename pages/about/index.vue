<template>
  <v-content>
    <v-container class="pa-0">
      <v-row>
        <v-col md="1"></v-col>
        <v-col xs="12" md="10" class="pa-0"
          ><v-img class="about-img" src="image/about/about_message.png"></v-img
        ></v-col>
        <v-col md="1"></v-col>
      </v-row>
      <p class="about_title text-center">Before Debut</p>
      <v-row>
        <v-col cols="12"><div class="line"></div></v-col>
        <v-col xs="12" md="6" class="pa-0"
          ><v-carousel show-arrows-on-hover height="350px" class="about-carousel">
            <v-carousel-item
              v-for="(item, index) in debuts"
              :key="index"
              :src="item.src"
              reverse-transition="fade-transition"
              transition="fade-transition"
            ></v-carousel-item> </v-carousel
        ></v-col>
        <v-col xs="12" md="6" class="abouttext1">
          <div class="text1">
            <p>
              2015年8月21日乃木坂46の関連グループとして、応募総数2万2509人の中、約1000分の1の狭き門をくぐり抜けた21人によって構成された欅坂46。
              AKB48の公式ライバルとして結成された乃木坂46の妹分になるのか、ライバルとなるのかというチームの立ち位置や、
              どのようなチームカラーになっていくのかファンから期待されていた。
            </p>
          </div>
        </v-col>
      </v-row>
      <p class="about_title text-center">1st Single released</p>
      <v-row>
        <v-col cols="12"><div class="line"></div></v-col>
        <v-col xs="12" md="6" class="pa-0"
          ><v-carousel show-arrows-on-hover height="350px" class="about-carousel">
            <v-carousel-item
              v-for="(item, index) in firsts"
              :key="index"
              :src="item.src"
              reverse-transition="fade-transition"
              transition="fade-transition"
            ></v-carousel-item> </v-carousel
        ></v-col>
        <v-col xs="12" md="6" class="abouttext2">
          <div class="text1">
            <p>
              彼女たちのデビュー曲である「サイレントマジョリティー」は、今までのTHEアイドルのようなイメージとは異なる迫力のある曲調と
              「自分らしさ」を歌った力強い楽曲でした。その後も、高度でクールなパフォーマンスやダークな楽曲と共に活動していきアイドルに
              対するイメージを大きく変化させ「アイドルを超えた存在」とまで言われるようになった。
            </p>
          </div>
        </v-col>
      </v-row>
      <p class="about_title text-center">THE LAST LIVE</p>
      <v-row>
        <v-col cols="12"><div class="line"></div></v-col>
        <v-col xs="12" md="6" class="pa-0"
          ><v-carousel show-arrows-on-hover height="350px" class="about-carousel">
            <v-carousel-item
              v-for="(item, index) in lasts"
              :key="index"
              :src="item.src"
              reverse-transition="fade-transition"
              transition="fade-transition"
            ></v-carousel-item> </v-carousel
        ></v-col>
        <v-col xs="12" md="6" class="abouttext3">
          <div class="text1">
            <p>
              2019年2月発売の8枚目シングル「黒い羊」以後、新しい楽曲が発売されていなかった状況や、
              結成当時からグループを支えてきた中核メンバーの卒業が相次ぎ、その中でも“絶対的センター”としてグループを代表する
              メンバーでもあった平手友梨奈の脱退、新メンバーの加入が契機となり改名、櫻坂46として心機一転新たなスタートを切ろうとしている。
            </p>
          </div>
        </v-col>
      </v-row>
      <p class="about_title text-center">Be Sakurazaka46...</p>
      <v-row>
        <v-col cols="12"><div class="line"></div></v-col>
        <v-col cols="12" class="pa-0"><v-img src="image/about/about_sakurazaka.jpg"></v-img></v-col>
        <v-col cols="12"
          ><div class="about_link">
            <nuxt-link to="history/sakurazaka">櫻坂46のページへ</nuxt-link>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </v-content>
</template>

<script>
export default {
  data() {
    return {
      debuts: [
        {
          src: 'image/about/debut/about_pic.jpg',
        },
        {
          src: 'image/about/debut/about_pic4.png',
        },
        {
          src: 'image/about/debut/about_pic2.jpeg',
        },
        {
          src: 'image/about/debut/about_pic3.jpeg',
        },
      ],
      firsts: [
        { src: 'image/about/first/about_first1.jpg' },
        { src: 'image/about/first/about_first2.jpeg' },
        { src: 'image/about/first/about_first3.jpeg' },
        { src: 'image/about/first/about_first4.jpeg' },
      ],
      lasts: [
        { src: 'image/about/lastlive/about_last.jpg' },
        { src: 'image/about/lastlive/about_last2.jpeg' },
        { src: 'image/about/lastlive/about_last3.jpeg' },
        { src: 'image/about/lastlive/about_last4.jpeg' },
      ],
    };
  },
};
</script>

<style>
.about_title {
  margin-top: 5vh;
  padding: 5px;
  font-size: 25px;
}
.line {
  margin: 0 auto;
  border-bottom: 1px solid;
  width: 10vw;
}
.aboutpicmain p {
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  position: absolute;
  top: 30%;
  left: 33%;
  font-size: 90px;
  color: white;
}
@media screen and (max-width: 800px) {
  .text1 {
    font-size: 1rem;
    line-height: 1.5rem;
  }
}
@media screen and (min-width: 801px) {
  .text1 {
    font-size: 1rem;
    line-height: 1.5rem;
  }
}
@media screen and (min-width: 1200px) {
  .text1 {
    font-size: 1.5rem;
    line-height: 2.5rem;
  }
}
.text1 {
  text-shadow: 3px 3px 2px #0f0f0f;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  background-color: rgba(27, 25, 25, 0.85);
  max-height: 400px;
  vertical-align: middle;
}
.text1::first-letter {
  font-size: 2em;
  float: left;
  padding: 5px;
}
.about_link {
  width: 200px;
  margin-left: auto;
  margin-right: auto;
}
a {
  color: white;
  font-size: 1.5rem;
}
</style>
