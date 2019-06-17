<template>
  <v-app>
    <v-content>
      <SpinButton/>
      <ZoomInButton/>
      <ZoomOutButton/>
      <TextField/>
    </v-content>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import SpinButton from './components/SpinButton'
import ZoomInButton from './components/ZoomInButton'
import ZoomOutButton from './components/ZoomOutButton'
import TextField from './components/TextField'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    SpinButton,
    ZoomInButton,
    ZoomOutButton,
    TextField
  },
  data () {
    return {

    }
  }
}
</script>

<style>

</style>
