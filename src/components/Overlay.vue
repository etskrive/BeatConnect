<template>
  <div>
    <div class="overlayBackground"></div>
    <div class="overlayContainer">
      <div class="btn cancel" v-on:click="showOverlay">X</div>
      <div class="overlayHeader">Join the community</div>
      <div class="btnContainer">
        <div class="loginRedirContainer">
          <label>Already have a user?</label> 
          <div class="btn dark">Login</div>
        </div>
        <div class="btnFacebook">Join using Facebook</div>
      </div>
      <p>or</p>
      <form class="" action="index.html" method="post">
        <label>First name</label>
        <input type="text" name="" value="">
        <label>Last name</label>
        <input type="text" name="" value="">
        <label>Email address</label>
        <input type="text" name="" value="">
        <label>Password</label>
        <input type="text" name="" value="">
        <label>Repeat Password</label>
        <input type="text" name="" value="">
        <input class="btn dark" type="submit" value="Join">
      </form>
      <div class="legaltextJoin">By joining, you agree to the <a href="#">Terms</a> and <a href="#">Privacy Policy</a>.</div>
    </div>    
  </div>
</template>

<script>
  import { overlayBus } from '../main';
  
  export default {
    date(){
      return{
        
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
  .overlayBackground {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 8888;
    background-color: var(--color-background-overlay);
    background-image: url('../assets/yguoyf9x6w451.jpg');
    background-size: cover;
    height: 100%;
    width: 100%;
  }
  .overlayContainer {
    position: relative;
    max-width: 40rem;
    min-width: 25rem;
    z-index: 9999;
    background-color: var(--color-background-alpha);
    padding: 4rem 6rem;
    font-size: 1.2rem;
    border-radius: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin: 10rem auto;
  }
  .overlayHeader {
    font-size: 2rem;
  }
  .btnContainer {
    width: 100%;
  }
  .loginRedirContainer {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    margin-bottom: 1.5rem;
  }
  .loginRedirContainer label {
    margin: 0 1.5rem 0 0 !important;
  }
  .btnFacebook {
    background-color: #3B5998;
    width: 100%;
    padding: 1.5rem 3rem;
    border-radius: 2rem;
    font-weight: 600;
  }
  .btnFacebook:active,
  .btnFacebook:hover {
    cursor: pointer;
  }
  .overlayContainer p {
    text-transform: uppercase;
  }
  .overlayContainer form {
    width: 100%;
    display: flex;
    flex-direction: column;
    text-align: left;
  }
  .overlayHeader,
  .overlayContainer form > *,
  .btnContainer {
    margin-bottom: 2rem;
  }
  .overlayContainer label {
    margin-bottom: .8rem;
  }
  .overlayContainer input {
    background-color: black;
    border: none;
    border-radius: 2rem;
    padding: 1.6rem 2rem;
    outline: none;
  }
  .overlayContainer .btn {
    align-self: center;
  }
  .btn.cancel {
    position: absolute;
    top: 1.5rem;
    right: 1.5rem;
    font-size: 1.2rem;
    color: white;
    border: 1px solid white;
    width: 2rem;
    height: 2rem;
    display: flex;
    justify-content: center;
    align-items:center;
    border-radius: 5rem;
    transition: all .2s;
  }
  .btn.cancel:active,
  .btn.cancel:hover {
    cursor: pointer;
    background-color: gray;
  }
  .btn.dark {
    height: 3rem;
    width: 8rem;
    background-color: var(--color-element-darker);
    color: var(--color-text);
    border: var(--main-border);  
    border-radius: 1.3rem;
    transition: .2s;
    text-align: center;
    padding: .6rem;
  }
  .btn.dark:hover,
  .btn.dark:active {
    cursor: pointer;
    background-color: gray;
  }
  .btn.dark:focus {
    outline: none;
  }
</style>
