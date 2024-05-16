<template>
  <v-app>
    <!-- <v-main>
      <router-view></router-view>
    </v-main> -->
    <input v-model="name" type="text" style="width: 200px; border: 2px solid blue; margin-top: 100px" />
    <button @click="call" style="width: 200px; background-color: yellow">Call</button>
  </v-app>
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
        console.log('NAME - ', this.name);
        setTimeout(() => {
          // cordova.plugins.CordovaCall.setAppName(this.name);
          cordova.plugins.CordovaCall.receiveCall(
            // cordova.plugins.CallKit.receiveCall(
            this.name,
            () => {
              console.log('Success call');
            },
            error => {
              console.log('Error calling - ', error);
            },
          );
        }, 1000);
      },
    },
  };
</script>

<style></style>
