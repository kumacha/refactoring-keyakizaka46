<template>
  <top-message :sub-title="sub" :main-title="title" :sub-date="date" />
</template>

<script>
import TopMessage from '~/components/Organisms/TopMessage.vue';
export default {
  components: {
    TopMessage,
  },
  data() {
    return {
      sub: 'HISTORY OF',
      title: '2期生',
      date: '20150821-20201013',
    };
  },
};
</script>

<style></style>
