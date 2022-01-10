<template>
  <div>
    {{ str }}
    <AppHeader v-on:renew="renewStr" v-bind:propsdata="str" />
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';

export default {
  data: function () {
    return {
      str: 'Test',
    };
  },
  components: {
    AppHeader,
  },
  methods: {
    renewStr: function () {
      this.str = 'hi';
    },
  },
};
</script>

<style></style>
