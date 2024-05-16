<template>
  <div>
    <input v-model="name" type="text" />
    <button @click="call">Call</button>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        name: '',
      };
    },
    methods: {
      call() {
        cordova.plugins.CordovaCall.receiveCall(this.name);
      },
    },
  };
</script>

<style lang="scss" scoped>
  div {
    background: #eee;
  }
</style>
