<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6> </v-flex>
    <v-carousel dark hide-delimiters max="1000" hide-controls>
      <v-carousel-item
        v-for="(item, i) in photos"
        :key="i"
        :src="item.src"
      ></v-carousel-item>
    </v-carousel>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      photos: [
        {
          src:
            'https://www.unr.edu/Images/student-services/greek-life/DSC00134.JPG'
        },
        { src: 'https://web.duke.edu/pbsigma/BrothersOnTheYard.jpg' },
        { src: 'https://www.csuchico.edu/fsa/_assets/images/pbsig.jpg' }
      ]
    }
  }
}
</script>
