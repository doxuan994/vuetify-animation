<template>
  <v-container>
    <v-layout row wrap>
      <v-flex>
        <div class="mx-3 lighten-1 pa-5">
          <div class="wrapper">
            <div class="innerWrapper">
              <v-btn class="zoomOutBtn" depressed fab dark color="light-blue darken-3" @click="zoom">
                <v-icon dark>add</v-icon>
              </v-btn>
            </div>
            <div class="innerWrapper2" >
              <div class="zoomOutCircle" :class="{ zoomOutGiant: isActive, zoomInGiant: isZoomIn }"></div>
            </div>
          </div>
        </div>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    isActive: false,
    isZoomIn: false,
    isZoomInDone: false,
    isBackgroundColorActive: false,
  }),
  methods: {
    zoom() {
      if (this.isActive == false) {
        this.isActive = true;
        this.isZoomIn = false;

      } else if (this.isActive == true) {
        this.isActive = false;
        this.isZoomIn = true;
      }
    }
  }
}
</script>

<style scoped>
* {
  box-sizing: border-box;
}

.wrapper {
  position: relative;
  background-color: #fff;

  width: 200px;
  height: 200px;
}

.innerWrapper {
  position: absolute;
  bottom: 70px;
  left: 50%;
  transform: translate(-50%);
  z-index: 1;
}
.innerWrapper2 {
  position: absolute;
  bottom: 76px;
  left: 50%;
  transform: translate(-50%);
}

.zoomOutBtn {
  /* box-shadow: none!important; */
}

.zoomOutBtn span {
  background-color: transparent;
  transition: none;
}
.v-ripple__container {
  background-color: #0277BD!important;
  transition: none;
}

.backgroundColorActive {
  background-color: #0277BD!important;
}


.zoomOutBtn:hover:before {
  background-color: transparent;
}
.zoomOutBtn::selection {
  background-color: transparent;
}
.zoomOutBtn:focus {
  background-color: transparent;
}
.zoomOutBtn:hover {
  background-color: transparent;
}

.zoomOutCircle {
  width: 56px;
  height: 56px;
  background-color: #0277BD;
  border-radius: 50%;
}

.zoomOutGiant {
  animation-name: zoomOutGiant;
  animation-duration: 0.5s;
  animation-iteration-count: 1;
  animation-timing-function: ease-in;
  animation-fill-mode: forwards;
}

@keyframes zoomOutGiant {
  0% {
    transform: scale(1);
  }
  100% {
    transform: scale(3);
  }
}

.zoomInGiant {
  animation-name: zoomInGiant;
  animation-duration: 0.5s;
  animation-iteration-count: 1;
  animation-timing-function: ease-in;
  animation-fill-mode: forwards;
}

@keyframes zoomInGiant {
  0% {
    transform: scale(3);
  }
  100% {
    transform: scale(1);
  }
}



</style>
