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
      sub: 'DEBUT OF',
      title: 'SAKURAZAKA46',
      date: '20201014 - re:start',
    };
  },
};
</script>

<style></style>
