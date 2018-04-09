<template>
  <div>
    <v-toolbar fixed class="" dark>
      <v-toolbar-side-icon class="hidden-md-and-up" @click="toggleDrawer"> </v-toolbar-side-icon>
      <v-avatar size="52px">
        <img src="../assets/logo_white.jpg">
      </v-avatar>
      <v-toolbar-title class="mr-4" fixed>
        <router-link to="/" class="home headerLink">
          <span>
            Jazz Illustrators
          </span>
        </router-link>
      </v-toolbar-title>

      <!-- <v-toolbar-items>
        <v-btn
          flat
          dark
          class="headerLink">-
          Browse
        </v-btn>
      </v-toolbar-items> -->

      <v-spacer></v-spacer>

      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn
          flat
          dark
          class="headerLink">
          Home
        </v-btn>

        <v-btn
          flat
          dark
          class="headerLink">
          Events
        </v-btn>

        <v-btn
          flat
          dark
          class="headerLink">
          About Us
        </v-btn>

        <v-btn
          flat
          dark
          class="headerLink">
          Contact
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>

    <v-navigation-drawer
      temporary
      v-model="drawer"
      absolute
      hide-overlay
     >
       <v-list class="pa-1">
         <v-list-tile avatar>
           <v-list-tile-avatar>
             <img src="../assets/logo_black.jpg">
           </v-list-tile-avatar>
           <v-list-tile-content>
             <v-list-tile-title>Jazz Illustrators</v-list-tile-title>
           </v-list-tile-content>
         </v-list-tile>
       </v-list>
       <v-list class="pt-0" dense>
         <v-divider></v-divider>
         <v-list-tile v-for="item in items" :key="item.title">
           <!-- <v-list-tile-action>
             <v-icon>{{ item.icon }}</v-icon>
           </v-list-tile-action> -->
           <v-list-tile-content>
             <v-list-tile-title class="ml-3">
               <router-link :to="item.href" class="headerLink">
                 <span>
                   {{item.title}}
                 </span>
               </router-link>
             </v-list-tile-title>
           </v-list-tile-content>
         </v-list-tile>
       </v-list>
     </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data () {
    return {
      drawer: null,
      drawerWasClosed: false,
      items: [
        { title: 'Home', icon: 'dashboard', href: '/#' },
        { title: 'Events', icon: 'dashboard', href: '/#' },
        { title: 'About', icon: 'dashboard', href: '/#' },
        { title: 'Contact', icon: 'question_answer', href: '/#' }
      ]
    }
  },

  watch: {
    drawer (val) {
      if (!val) {
        this.drawerWasClosed = true
        setTimeout(() => {
          this.drawerWasClosed = false
        }, 0)
      }
    }
  },
  methods: {
    toggleDrawer () {
      this.drawer = !this.drawerWasClosed
    }
    // mobileScreen () {
    //   if (window.innerWidth < 993) {
    //     return
    //   }
    // }
  }
}
</script>
<style scoped>
.headerLink, .headerLink:hover{
  /* border: 1px solid red; */
  text-decoration: none
}
</style>
