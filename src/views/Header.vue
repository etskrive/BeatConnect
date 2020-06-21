<template lang="html">
  <div class="headerContainer sectionElement">
      <div class="logoContainer">
        <div class="logoContainer__logoWrapper">
          <svg><use xlink:href="../assets/symbol-defs.svg#icon-beatConnectLogo"></use></svg>
        </div>
        <div class="logoContainer__text">Beat Connect</div>
      </div>
      <div class="navElements">
        <div class="navElement__choice">Discover</div>
      </div>
      <div class="navElements">
        <div class="navElement__choice">Profile</div>
      </div>
      <div class="profileContainer">
        <div class="profileContainer__text" v-on:click="showOverlay">{{ profilePrompt }}</div>
      </div>
  </div>
</template>

<script>
import { overlayBus } from '../main';

export default {
  props: {

  },
  // components: {

  // },
  data(){
    return {
      profilePrompt: "Sign up"
    }
  },
  methods: {
    showOverlay: function(){
      overlayBus.$emit('showOverlay');
    }
  }
}
</script>

<style lang="css" scoped>
  .headerContainer {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    height: 6rem;
    background-color: var(--color-element-header);
    border: var(--main-border);
    border-radius: 1.5rem;
  }
  .headerContainer > * {
    padding: 2rem 5rem;
  }
  .logoContainer {
    display: flex;
    flex-direction: row;
    align-items: center;
  }
  .logoContainer .logoContainer__logoWrapper {
    height: 4.5rem;
    width: 4.5rem;
    background-image: url('../assets/svg/beatConnectLogo.svg');
    background-size: cover;
    margin-right: 1rem;
  }
  .logoContainer .logoContainer__text {
    font: italic small-caps bold 44px Jazz LET, fantasy;
    font-size: 2rem;
  }
  .navElement {

  }
  .navElement__choice {
    font-size: var(--text-header);
    cursor: pointer;
    user-select: none;

  }
  .profileContainer {
    transition: all .2s;
  }
  .profileContainer:hover {
    border-radius: 0 1.2rem 1.2rem 0;
    border: 1px 1px 1px 0 red solid;
    background-color: teal;
    cursor: pointer;
  }
  .profileContainer .profileContainer__text {
    font-size: var(--text-header);
  }
</style>
