<template>
  <div id="app-beatConnect">

    <app-overlay v-if="overlayVisible == true"></app-overlay>
    <app-header></app-header>

    <!-- <div style="text-align:left;">
      Testbuttons:
      <button style="color:black; font-size:1rem;"
      type="button" name="button">One</button>
      <button style="color:black; font-size:1rem;"
      type="button" name="button">Two</button>
      <button style="color:black; font-size:1rem;"
      type="button" name="button">Three</button>
    </div> -->

    <page-discover></page-discover>
    <page-profile></page-profile>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Overlay from './components/Overlay.vue'
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Discover from './components/Discover.vue'
import Profile from './components/Profile.vue'

import { overlayBus } from './main';

export default {
  name: 'App',
  overlayVisible: false,
  components: {
    'app-overlay': Overlay,
    'app-header': Header,
    'app-footer': Footer,
    'page-discover': Discover,
    'page-profile': Profile
  },
  data(){
    return {
      overlayVisible: false
    }
  },
  created(){
    overlayBus.$on('showOverlay', () => {
      this.overlayVisible = !this.overlayVisible;
      console.log(this.overlayVisible);
      this.overlayLocation = "";
    })
  }
}
</script>

<style>
  :root {
    --color-background-alpha: rgba(20,20,20,1);
    --color-background: rgba(150,150,150,.3);
    --color-background-overlay: rgba(50,50,50,1);
    --color-element: rgba(150,150,150,.3);
    --color-element-darker: rgba(20,20,20,.6);
    --color-element-header: rgba(20,20,20,.1);
    --color-border: rgba(200,200,220,.4);
    --color-text: rgba(250,250,250,1);
    --color-text-placeholder: rgba(250,250,250,.7);
    --color-text-hover: blue;
    --color-text-link: blue;
    --color-text-link-hover: blue;
    --color-button: blue;
    --color-button-hover: blue;
    --color-btn-filter-active: rgba(120,120,250,.6);
    --color-choice-hover: rgba(120,120,250,.6);
    --color-navbar: blue;
    --color-navbar-button: blue;
    --color-navbar-button-hover: blue;

    --main-border: 2px var(--color-border) solid;

    --text-header: 1.8rem;
  }
  html {
    font-size: 62.5%;
  }
  body {
    /* background-color: var(--color-background); */
    background-image: url('./assets/ezsxcgajug551.jpg');
    background-size: auto;
    /* font: normal small-caps normal 1.6rem Georgia; */
    font: normal normal 12px Georgia, sans-serif; /* fallback for older browsers */
  }
  #app-beatConnect {
    /* font-family: Avenir, Helvetica, Arial, sans-serif; */
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin: 4rem;
  }
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    color: var(--color-text);
  }
  .sectionHeader {
    font-size: 4rem;
    letter-spacing: 1rem;
  }
  .sectionElement {
    background-color: var(--color-element);
    border: var(--main-border);
    border-radius: 1.5rem;
    width: 100%;
  }
</style>
