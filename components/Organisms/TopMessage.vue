<template>
  <v-container>
    <v-row style="height: 70vh" justify="center" align-content="center">
      <div class="logo">
        <p class="hislogo sublogo" v-text="subTitle"></p>
        <p class="keyakilogo biglogo" v-text="mainTitle"></p>
        <p class="dayslogo sublogo" v-text="subDate"></p>
      </div>
    </v-row>
  </v-container>
</template>

<script>
export default {
  props: {
    subTitle: {
      required: true,
      type: String,
    },
    mainTitle: {
      required: true,
      type: String,
    },
    subDate: {
      required: true,
      type: String,
    },
  },
};
</script>

<style>
.hislogo {
  color: #ffffff;
  font-family: 'Cinzel', serif;
  position: relative;
  margin: 0;
  text-align: left;
  top: 3vh;
}
.keyakilogo {
  color: #ffffff;
  font-family: 'Cinzel', serif;
  margin: 0;
  padding: 0, 0;
  position: relative;
  text-align: center;
  z-index: 0;
}
.dayslogo {
  color: #ffffff;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  position: relative;
  text-align: center;
  margin: 0;
  bottom: 3vh;
}
.logo p {
  text-shadow: 1px 1px 1px #0f0f0f;
}
@media screen and (max-width: 800px) {
  .biglogo {
    font-size: 3rem;
  }
  .sublogo {
    font-size: 1.2rem;
  }
}
@media screen and (min-width: 801px) {
  .biglogo {
    font-size: 4.5rem;
  }
  .sublogo {
    font-size: 1.4rem;
  }
}
@media screen and (min-width: 1200px) {
  .biglogo {
    font-size: 5rem;
  }
  .sublogo {
    font-size: 1.6rem;
  }
}
</style>
