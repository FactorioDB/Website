<template>
</template>

<script>
  import Container from '../partials/Container';
  import router from '../../router';
  import store from '../../store';

  export default {
    name: 'login-view',
    components: {
      Container
    },
    mounted() {
      this.$watch(() => store.getters.user, () => {
        router.replace(router.currentRoute.query.redirect || '/');
      });
      this.$parent.$refs.nav.openLoginDialog();
    }
  };
</script>

<style lang="scss" scoped>

</style>
