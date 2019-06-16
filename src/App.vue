<template>
  <v-app>
    <!-- <v-toolbar app>

    </v-toolbar> -->

    <v-content>
      <SpinButton/>
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import SpinButton from './components/SpinButton'

export default {
  name: 'App',
  components: {
    HelloWorld,
    SpinButton
  },
  data () {
    return {

    }
  }
}
</script>
