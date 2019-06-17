<template>
  <v-container>
    <v-layout row wrap>
      <v-flex xs12 md4>
        <div class="mx-3 grey lighten-1 pa-5">
          <div class="loader">
            <!-- <svg class="circular-loader" viewBox="-4 -4 78 78"><circle class="loader-path" cx="35" cy="35" r="32" fill="white" stroke="#f4511e" stroke-width="9" /></svg> -->
            <svg viewBox="-3 -3 106 106" style="display: block; width: 100%;" class="circular-loader">
              <path d="M 50,50 m 0,-47.5 a 47.5,47.5 0 1 1 0,95 a 47.5,47.5 0 1 1 0,-95" stroke="white" stroke-width="9" fill-opacity="0"></path>
              <path class="loader-path" d="M 50,50 m 0,-47.5 a 47.5,47.5 0 1 1 0,95 a 47.5,47.5 0 1 1 0,-95" stroke="#F4511E" stroke-width="9" fill-opacity="0"></path>
            </svg>
            <v-btn fab dark color="deep-orange darken-1" class="spinBtn">
              <v-icon dark>add</v-icon>
            </v-btn>

          </div>
          <!-- <v-btn fab dark color="deep-orange darken-1">
            <v-icon dark>add</v-icon>
          </v-btn>
          <v-btn fab dark color="blue-grey darken-3">
            <v-icon dark>done</v-icon>
          </v-btn> -->
        </div>
      </v-flex>
      <v-flex xs12 md4>
        <div class="mx-3 deep-purple darken-3 pa-5"></div>
      </v-flex>
      <v-flex xs12 md4>
        <div class="mx-3 white pa-5"></div>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({

  })
}
</script>

<style>
* {
  box-sizing: border-box;
}

/* Button inside  */
.spinBtn {
  margin: 7px 7px;
}





/* SVG Cirlce */
.loader {
  position: relative;
  margin: 6px 8px;
  width: 70px;
  height: 70px;
}

/* Spin */
.circular-loader {
  transform: rotate(-45deg);
  animation: rotate 0.8s linear 1;
  height: 100%;
  transform-origin: center center;
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  margin: auto;

  width: 70px;
  height: 70px;

  /* background-color: gold; */
}

/* Define spin path */
.loader-path {
  stroke-dasharray: 200,200;
  stroke-dashoffset: 0;
  stroke-linecap: round;
  /* paint-order: stroke; */

  /* animation: dash 1.5s ease-in-out infinite, color 6s ease-in-out infinite; */
  animation: dash 0.8s ease-in-out 1 forwards;
}


@keyframes rotate {
  100% {
    transform: rotate(315deg);
  }
}






@keyframes dash {
  0% {
    stroke-dasharray: 1, 200;
    stroke-dashoffset: 0;
  }
  /* 100% {
  stroke-dasharray: 1, 200;
  stroke-dashoffset: 0;
  } */
}







/* @keyframes color {
0% {
stroke: #F4511E;
}
40% {
stroke: #F4511E;
}
66% {
stroke: #F4511E;
}
80%, 90% {
stroke: #F4511E;
}
} */
</style>
