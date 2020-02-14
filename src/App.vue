<template>
  <v-app>
    <v-content>
      <v-container v-if="showButton" class="fill-height justify-center" fluid>
        <v-container fluid class="text-center font-weight-normal">
          <v-btn
            large
            color="error"
            @click.prevent="playPixies('http://cthulhu22.free.fr/Pixies%20-%20Wave%20Of%20Mutilation%20The%20Best%20Of%20Pixies%20(2004)%20320%20vtwin88cube/08.Hey.mp3')"
          >{{ this.buttonTex }}</v-btn>
        </v-container>
      </v-container>

      <v-container class="fill-height justify-center" fluid>
        <v-row align="center" justify="center">
          <v-col cols="12" sm="8" md="4">
            <HelloWorld v-if="showLyrics" />
          </v-col>
        </v-row>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    HelloWorld
  },
  data() {
    return {
      showLyrics: false,
      showButton: true,
      buttonTex: `I'm ready <3`
    };
  },
  methods: {
    playPixies(hey) {
      if (hey) {
        this.showLyrics = true;
        this.showButton = false;
        var audio = new Audio(hey);
        audio.play();
      }
    }
  },
  mounted() {
    console.log("Te amo, Guillermo. Feliz San Valentín <3 PRRR");
  }
};
</script>
<style lang="css">
#app {
  font-family: "Courier New", serif;
}
</style>
