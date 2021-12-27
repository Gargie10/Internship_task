<template>
<v-app>
  <v-row>
    
    <v-app-bar
      color="black"
      dark>
      <v-col  class="d-flex  pl-16">
      <v-toolbar-title >Support : +91 - 9090909090</v-toolbar-title>
      </v-col>
     

      <v-col  class="d-flex justify-space-around ">
      <v-toolbar-title class="pt-3 d-flex justify-space-start" ><span class="red--text">Book a FREE Test Ride Now </span></v-toolbar-title>
      </v-col>
      <v-col class="d-flex justify-space-around ">
      <v-btn icon @click="showAbout">
        Contact
      </v-btn>

      <v-btn icon @click="showAbout">
      Career
      </v-btn>

      <v-menu
        left
        bottom
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            icon
            v-bind="attrs"
            v-on="on"
          >
          Media
            <v-icon>mdi-chevron-down</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item
            v-for="n in 5"
            :key="n"
            @click="() => {}"
          >
            <v-list-item-title>Option {{ n }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
     </v-col>
    </v-app-bar>
 
</v-row>
<v-row>
  <v-app-bar
      color="black"
      dark>
       <v-col class="d-flex  pl-16">
        <v-avatar :tile="true">
          <img :src="require('@/assets/Logo (2).png')" alt="Logo (2)">
        </v-avatar>
      </v-col>

      <v-col class="d-flex justify-space-between">

      <v-btn icon @click="showAbout">
        About
      </v-btn>

      <v-btn icon @click="showAbout">
       Locate Store
      </v-btn>

       <v-btn icon v-on:click="isHidden = !isHidden" >
       Scootors
        <v-icon>mdi-chevron-down</v-icon>
      </v-btn>
    
      <v-menu
        left
        bottom
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            icon
            v-bind="attrs"
            v-on="on"
          >
        Purchase <br> Assistance
            <v-icon>mdi-chevron-down</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item
           v-for="(item, index) in items"
          :key="index"
          >
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      
      <v-btn
      depressed
      color="red" @click="showAbout">
     <span class="white--text">Dealership </span>
    </v-btn>
    </v-col>
    </v-app-bar>
</v-row>

    <template> 
    <v-tabs v-model="tab"
      color="grey" v-if="!isHidden" centered>
          <v-tabs-slider color="red"></v-tabs-slider>
        <v-tab ><h1>HRX 350 BIKE</h1></v-tab>
        <v-tab><h1>GEAR 350 EB</h1></v-tab>
        <v-tab><h1>RX-AK 290 EB</h1></v-tab>
        <v-tab><h1>GMB-Heavy</h1></v-tab>
        <v-tab><h1>GMB-Light</h1></v-tab>
      </v-tabs>
    </template>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  

  data: () => ({
    tab: null,

     items: [
        { title: 'Buy Scootors' },
        { title: 'Buy Bikes' },
        { title: 'Repairing' },
        { title: 'Exchange' },
      ],

     isHidden: true,
      
  }),

methods: {
   showAbout() {
      this.$router.push({name:'About'})
  },
}   
};


</script>
