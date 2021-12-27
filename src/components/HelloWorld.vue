<template>
  <v-container>
    <v-row class="text-center">
      <v-col >
     <v-carousel cycle
    height="700"
    backgrround-color="black"
    
    show-arrows-on-hover>
    <v-carousel-item
      v-for="color in colors"
      :key="color"
    >
    <template>
        <div class="text-center">
            <v-progress-circular
            :size="700"
            color="black"
            indeterminate
            > <v-img
                :src="require('../assets/model.png')"
                class="my-3"
                contain
                height="650"
                />
            </v-progress-circular>
        </div>
    </template>
      </v-carousel-item>
  </v-carousel>
        <!-- <v-img
          :src="require('../assets/model.png')"
          class="my-3"
          contain
          height="650"
        >
        
        <template v-slot:placeholder>
        <v-row
          class="fill-height ma-0"
          align="center"
          justify="center"
        >
        <v-img
          :src="require('../assets/74499-circle.gif')"
          class="my-3"
          contain
          height="650"
        />
        
        </v-row>
        </template>
        </v-img> -->
      </v-col>

      <v-col class="mb-4 pt-12 ">
          <v-row class="justify-center mt-12">
        <h1 class="display-2 font-weight-bold mt-12 mb-9">
          "Life is a Journey, 
          <br>Enjoy the ride"
        </h1>
          </v-row>

        <div >
        <p class="subheading font-weight-regular justify-start mt-12 mx-auto">
          A neat sample text to come here super soon. Till then admire the authentic and delightful User Interface Design of the Website. We are glad you came here , thanks for visiting . 
        </p>
        </div>

    <v-btn @click="showAbout"
      depressed
      color="red">
      <span class="white--text">Show Details </span>
    </v-btn>
      

     
     </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'Homepage',

    data: () => ({
     model: 0,
      colors: [
        'primary',
        'secondary',
        'yellow darken-2',
        'red',
        'orange',
      ],
    }),
    methods: {
   showAbout() {
      this.$router.push({name:'About'})
  },
} 
  }
</script>
