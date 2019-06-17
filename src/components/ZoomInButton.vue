<template>
  <v-container>
    <v-layout row wrap>
      <v-flex>
        <div class="mx-3 lighten-1 pa-5">
          <div class="wrapper">
            <v-btn fab dark color="grey lighten-2" class="bus icon" :class="{ shooting: isActive }" v-show="isActive">
              <v-icon dark>directions_bus</v-icon>
            </v-btn>
            <v-btn fab dark color="grey lighten-2" class="plane icon" :class="{ shooting: isActive }" v-show="isActive">
              <v-icon dark>airplanemode_active</v-icon>
            </v-btn>
            <v-btn fab dark color="grey lighten-2" class="boat icon" :class="{ shooting: isActive }" v-show="isActive">
              <v-icon dark>directions_boat</v-icon>
            </v-btn>
            <div class="innerWrapper">
              <v-btn class="zoomBtn" fab dark color="yellow darken-1" :class="{ zoomIn: isActive }" @click="isActive = !isActive">
                <v-icon dark v-if="!isActive">more_horiz</v-icon>
                <v-icon dark v-else>close</v-icon>
              </v-btn>
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
  }),
  methods: {

  },
  created() {

  }
}
</script>

<style scoped>
* {
  box-sizing: border-box;
}

.wrapper {
  position: relative;

  background-color: #607D8B;

  width: 200px;
  height: 120px;
}

.innerWrapper {
  position: absolute;
  bottom: 0px;
  left: 50%;
  transform: translate(-50%);
}

.icon {

}

.zoomBtn {
  box-shadow: none!important;
}
.zoomIn {
  transform: scale(0.5);
}


.plane {
  box-shadow: none!important;
  width: 40px;
  height: 40px;
  position: absolute;
  left: 37%;
}

.bus {
  box-shadow: none!important;
  width: 40px;
  height: 40px;
  position: absolute;
  left: 5%;
  top: 40px;
}

.boat {
  box-shadow: none!important;
  width: 40px;
  height: 40px;
  position: absolute;
  top: 40px;
  left: 65%;
}





.shooting {
  animation-name: shooting;
  animation-duration: 0.5s;
  animation-timing-function: ease-in;
  animation-fill-mode: forwards;
  animation-iteration-count: 1;
}

@keyframes shooting {
  0% {
    transform: scale(0.2);
  }
  100% {
    transform: scale(1);
  }
}



</style>
