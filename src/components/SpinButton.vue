<template>
  <v-container>
    <v-layout row wrap>
      <v-flex>
        <div class="mx-3 lighten-1 pa-5" >
          <div class="loader" @click="spin">
            <svg class="circular-loader" viewBox="-4 -4 108 108" v-show="active">
              <path d="M 50,50 m 0,-47.5 a 47.5,47.5 0 1 1 0,95 a 47.5,47.5 0 1 1 0,-95" stroke="white" stroke-width="12" fill-opacity="0"></path>
              <path class="loader-path" d="M 50,50 m 0,-47.5 a 47.5,47.5 0 1 1 0,95 a 47.5,47.5 0 1 1 0,-95" stroke="#F4511E" stroke-width="12" fill-opacity="0"></path>
            </svg>
            <v-btn depressed fab dark color="deep-orange darken-1" class="spinBtn" v-if="buttonShow">
              <v-icon dark>add</v-icon>
            </v-btn>
            <v-btn depressed fab dark color="blue-grey darken-3" class="spinBtn" v-else>
              <v-icon dark>done</v-icon>
            </v-btn>
          </div>
        </div>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    active: false,
    buttonShow: true,
    isSubmit: false,
  }),
  methods: {
    spin() {
      let vm = this;

      if (this.isSubmit == false) {
        this.active = true;
        this.isSubmit = true;
      }

      setTimeout(function() {
        vm.active = false;
        vm.buttonShow = false;
      }, 1000);
    }
  }
}
</script>

<style scoped>
* {
  box-sizing: border-box;
}
.loader {
  position: relative;
  width: 70px;
  height: 70px;
}


.circular-loader {
  animation: rotate 0.8s linear 1;
  height: 100%;
  transform-origin: center center;
  width: 100%;
  position: absolute;
  top: 0px;
  left: 0.5px;
  margin: auto;

  width: 70px;
  height: 70px;
}

/* Define spin path */
.loader-path {
  stroke-dasharray: 300,300;
  stroke-dashoffset: 0;
  stroke-linecap: square;
  animation: dash 0.8s ease-in-out 1 forwards;
}


@keyframes rotate {
  100% {
    transform: rotate(315deg);
  }
}


@keyframes dash {
  0% {
    stroke-dasharray: 1, 300;
    stroke-dashoffset: 0;
  }
}




</style>
