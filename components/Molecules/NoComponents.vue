<template>
  <div class="gomi">
    <div class="hamburger_btn" @click="ActiveBtn = !ActiveBtn">
      <span class="line line_01" :class="{ btn_line01: ActiveBtn }"></span>
      <span class="line line_02" :class="{ btn_line02: ActiveBtn }"></span>
      <span class="line line_03" :class="{ btn_line03: ActiveBtn }"></span>
    </div>
    <!--サイドバー-->
    <transition name="menudesu">
      <div v-if="ActiveBtn" class="menudesu">
        <div class="menu__item">
          <p class="menu-parts" @click="trigger({ path: '/' })">TOP</p>
          <p class="menu-parts" @click="trigger({ path: '/about' })">ABOUT</p>
          <p class="menu-parts" @click="trigger({ path: '/history' })">HISTORY</p>
          <p class="sub-parts" @click="trigger({ path: '/history/sakurazaka' })">- SAKURAZAKA'</p>
          <p class="menu-parts" @click="trigger({ path: '/discography' })">DISCOGRAPHY</p>
          <p class="menu-parts" @click="trigger({ path: '/member' })">MEMBER</p>
          <p class="sub-parts" @click="trigger({ path: '/member/first' })">- 1期生x</p>
          <p class="sub-parts" @click="trigger({ path: '/member/second' })">- 2期生</p>
          <p class="menu-parts" @click="trigger({ path: '/gallery' })">GALLERY</p>
          <p class="menu-parts" @click="trigger({ path: '/link' })">LINK</p>
          <!-- <div v-if="menu.sub">
            <p class="sub-parts" @click="trigger({ path: menu.path[1] })" v-text="menu.sub[0]"></p>
            <p class="sub-parts" @click="trigger({ path: menu.path[2] })" v-text="menu.sub[1]"></p>
          </div> -->
        </div>
      </div>
    </transition>
  </div>
  <!--ハンバーガーメニューのボタン-->
</template>

<script>
export default {
  components: {},
  data() {
    return {
      ActiveBtn: false,
      windowWidth: 900,
      menus: [
        { id: 1, name: 'TOP', path: ['/'] },
        { id: 2, name: 'ABOUT', path: ['/about'] },
        {
          id: 3,
          name: 'HISTORY',
          sub: ['- SAKURAZAKA'],
          path: ['/history', '/history/sakurazaka'],
        },
        { id: 4, name: 'DISCOGRAPHY', path: ['/discography'] },
        {
          id: 5,
          name: 'MEMBER',
          sub: ['- 1期生', '- 2期生'],
          path: ['/member', '/member/first', '/member/second'],
        },
        { id: 6, name: 'GALLERY', path: ['/gallery'] },
        { id: 7, name: 'LINK', path: ['/link'] },
      ],
    };
  },
  computed: {
    /**
     * スマホかどうかを判定する
     *
     * @return {Boolean}
     */
    isMobile() {
      return this.windowWidth < 900;
    },
  },
  mounted() {
    this.windowWidth = window.innerWidth;
    this.$nextTick(() => {
      window.addEventListener('resize', () => {
        this.windowWidth = window.innerWidth;
      });
    });
  },
  methods: {
    trigger(link) {
      if (this.isMobile) {
        this.ActiveBtn = false;
        this.$router.push(link);
      } else {
        this.$router.push(link);
      }
    },
  },
};
</script>

<style>
.gomi {
  z-index: 100;
}
/*ボタン*/
.hamburger_btn {
  position: fixed; /*常に最上部に表示したいので固定*/
  top: 0;
  right: 0;
  width: 40px;
  height: 16px;
  cursor: pointer;
  z-index: 50;
}

.hamburger_btn .line {
  position: absolute;
  top: 0;
  width: 20px;
  height: 2px;
  background-color: #fff;
  text-align: center;
}

.hamburger_btn .line_01 {
  top: 16px;
  transition: 0.4s ease;
}
.hamburger_btn .line_02 {
  top: 23px;
  transition: 0.4s ease;
}
.hamburger_btn .line_03 {
  top: 30px;
  transition: 0.4s ease;
}

.btn_line01 {
  transform: translateY(4px) rotate(-45deg);
  transition: 0.4s ease;
}
.btn_line02 {
  transition: 0.4s ease;
  opacity: 0;
}
.btn_line03 {
  transform: translateY(-10px) rotate(45deg);
  transition: 0.4s ease;
}

/*サイドバー*/
.menudesu-enter-active,
.menudesu-leave-active {
  transition: opacity 0.4s;
}
.menudesu-enter,
.menudesu-leave-to {
  opacity: 0;
  transform: translateX(0);
}
.menudesu-leave,
.menudesu-enter-to {
  transform: translateX(100vw);
}

.menudesu {
  background-color: black;
  opacity: 80%;
  z-index: 30;
  position: fixed;
  width: 100vw;
  height: 100vh;
  top: 0;
  right: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
