<template>
  <v-container>
    <v-layout row wrap>
      <v-flex xs12 sm6>
        <v-text-field
        class="text-color"
        :suffix="mySuffix"
        background-color="green accent-3"
        color="grey darken-4"
        box
        label="What's your name?"
        append-icon="arrow_forward"
        :loading="isActive"
        @click:append="nextInput"
        ></v-text-field>
      </v-flex>
    </v-layout>
  </v-container>
</template>



<script>
export default {
  data: () => ({
    mySuffix: '1/2',
    isActive: false,
  }),
  methods: {
    nextInput() {
      let vm = this;
      vm.isActive = true;

      setTimeout(function() {
        vm.mySuffix = '2/2';
        vm.isActive = false;
      }, 2000);


    }
  },
  created() {

  }
}
</script>

<style>
* {
  box-sizing: border-box;
}
.text-color input {
  color: #E53935 !important;
}

</style>
