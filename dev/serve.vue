<script>
import Vue from 'vue';
import Vue2CustomInput from '@/vue2-custom-input.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    Vue2CustomInput
  }
});
</script>

<template>
  <div id="app">
    <vue2-custom-input placeholder="username"/>
  </div>
</template>
