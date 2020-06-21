<template>
  <div class="feedInputUser">
    <div class="feedInputUser__header">
      <div class="feedInputUser__header--left">
        <div class="userImgWrapper"></div>
        <div class="userNameContainer">
          <div class="feedInputUserName">A username</div>
          <div class="feedInputUserTitle">Artist</div>
        </div>
      </div>
      <div class="feedInputUser__header--buttonCollection">
        <a href="#" class="feedInputBtn">
          <svg><use xlink:href="../assets/symbol-defs.svg#icon-music"></use></svg>
        </a>
        <a href="#" class="feedInputBtn">
          <svg><use xlink:href="../assets/symbol-defs.svg#icon-display"></use></svg>
        </a>
        <a href="#" class="feedInputBtn">
          <svg><use xlink:href="../assets/symbol-defs.svg#icon-message-circle"></use></svg>
        </a>
        <a href="#" class="feedInputBtn bookmark">
          <svg><use xlink:href="../assets/symbol-defs.svg#icon-bookmark"></use></svg>
        </a>
      </div>
    </div>
    <div class="feedInputUser__title">Someone want to collaborate with me on a project akin to this?</div>
    <div class="feedInputUser__sneakpeek">
      <div id="img1" class="feedInputUser__sneakpeek--imgWrapper"></div>
      <audio src="../assets/sample1.mp3" id="audio" controls>HTML5 Audio element not supported</audio>
    </div>
    <div class="feedInputUser__msgContainer">
      <form action="submit">
        <input class="quickMsgBox" type="text" placeholder="Send a private message">
        <input class="btn dark msg" type="submit" value=">">
      </form>
    </div>
  </div>
</template>

<script>
export default {
  
}
</script>

<style lang="css" scoped>
.feedInputUser {
  padding: 1rem 2rem;
  margin-bottom: 2rem;
}
.feedInputUser > *:not(:last-of-type) {
  margin-bottom: 2rem;
}
.feedInputUser__header {
  display: flex;
  justify-content: space-between;
}
.feedInputUser__header--left {
  display: flex;
  flex-direction: row;
  align-items: center;
}
.userNameContainer {
  display: flex;
  flex-direction: column;
}
.feedInputUserName {
  font-size: 1.6rem;
  font-weight: 600;
  margin-bottom: .3rem;
}
.feedInputUserTitle {
  font-size: 1.4rem;
  text-align: left;
}
.bar-wrapper {
  height: 300px;
  position: relative;
}

.bar {
  position: relative;
  bottom: 0;
  width: 5px;
  display: inline-block;
  border: 1px solid red;
  height: 5px;
  border-bottom: 3px solid #fff;
}

.userImgWrapper {
  background-image: url("../assets/profile.jpeg");
  background-position: center;
  background-size: cover;
  height: 5rem;
  width: 5rem;
  margin-right: 1rem;
  border-radius: 5rem;
  border: var(--main-border);
}
.feedInputUser__header--buttonCollection {
  display: flex;
  flex-direction: row;
}
.feedInputBtn {
  border: 1px solid rgba(200,200,200,.4);
  height: 3.5rem;
  width: 3.5rem;
  border-radius: 5rem;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: .2s;
}
.feedInputBtn svg {
  height: 2rem;
  width: 2rem;
  fill: white;
}
.feedInputBtn:hover,
.feedInputBtn:active {
  background-color: gray;
}
.feedInputBtn.bookmark {
  border: none;
}
.feedInputBtn.bookmark:hover,
.feedInputBtn.bookmark:active {
  background-color: inherit;
}
.feedInputBtn:not(:last-of-type) {
  margin-right: 0.5rem;
}
.feedInputUser__title {
  font-size: 1.8rem;
  text-align: left;
}
.feedInputUser__sneakpeek {
  display: flex;
  justify-content: row;
}
.feedInputUser__sneakpeek #img1 {
  background-image: url("../assets/anders-thomasson-scZEblckRmM-unsplash.jpg");
}
.feedInputUser__sneakpeek #img2 {
  background-image: url("../assets/anders-thomasson-scZEblckRmM-unsplash.jpg");
}
.feedInputUser__sneakpeek--imgWrapper {
  height: 6rem;
  width: 8rem;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  border-radius: .5rem;
  margin-right: 1.5rem;
}
.feedInputUser__sneakpeek audio {
  width: 100%;
}
.feedInputUser__msgContainer {
  display: flex;
  width: inherit;
  max-width: inherit;
}
.feedInputUser__msgContainer form {
  width: 100%;
  display: flex;
  justify-content: space-between;
}
.quickMsgBox {
  height: 4rem;
  width: 100%;
  background-color: var(--color-element-darker);
  color: white;
  padding: 1rem 1.5rem;
  border-radius: 1.5rem;
  border: none;
  margin-right: .8rem;
  outline: none;
}
.quickMsgBox::placeholder {
  color: var(--color-text-placeholder);
}
.btn.dark {
  height: 3rem;
  width: 8rem;
  background-color: var(--color-element-darker);
  color: var(--color-text);
  border: var(--main-border);  
  border-radius: 1.3rem;
  transition: .2s;
}
.btn.dark:hover,
.btn.dark:active {
  cursor: pointer;
  background-color: gray;
}
.btn.dark.msg {
  height: 4rem;
  width: 4.5rem;
  border-radius: 5rem;
}
</style>
