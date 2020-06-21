<template lang="html">
  <div class="sectionContainer">
    <div class="sectionHeader">{{ title }}</div>
    <div class="sectionChannels">
      <div class="sectionFeed">
        <div class="sectionFilter sectionElement minWidth">
          <div class="filterToggle noMargin" @click="showFilters">Filters</div>
            <div class="sectionFilter__sub">
              <div class="sectionFilter__subName">Your skills</div>
              <div class="sectionFilters__choices">
                <div class="filterChoice" @click="runFilter">
                  <svg><use xlink:href="../assets/symbol-defs.svg#icon-equalizer2"></use></svg>
                  <div class="filterChoice__name">Wing instruments</div>
                </div>
                <div class="filterChoice" @click="runFilter">
                  <svg><use xlink:href="../assets/symbol-defs.svg#icon-equalizer2"></use></svg>
                  <div class="filterChoice__name">Wing instruments</div>
                </div>
                <div class="filterChoice" @click="runFilter">
                  <svg><use xlink:href="../assets/symbol-defs.svg#icon-equalizer2"></use></svg>
                  <div class="filterChoice__name">Wing instruments</div>
                </div>
                <div class="filterChoice" @click="runFilter">
                  <svg class="svg--choice"><use xlink:href="../assets/symbol-defs.svg#icon-equalizer2"></use></svg>
                  <div class="filterChoice__name">Rap/rythic</div>
                </div>
                <div class="filterChoice" @click="runFilter">
                  <svg class="svg--choice"><use xlink:href="../assets/symbol-defs.svg#icon-equalizer2"></use></svg>
                  <div class="filterChoice__name">Song/harmony</div>
                </div>
                <div class="filterChoice" @click="runFilter">
                  <svg class="svg--choice"><use xlink:href="../assets/symbol-defs.svg#icon-equalizer2"></use></svg>
                  <div class="filterChoice__name">Stringed instruments</div>
                </div>
              </div>
            </div>

            <div class="sectionFilter__sub">
              <div class="sectionFilter__subName">Location</div>
              <form action="#" class="searchbarContainer">
                <svg class="icon-search"><use xlink:href="../assets/symbol-defs.svg#icon-search"></use></svg>
                <input type="text" class="searchbar" placeholder="Search location" />
                <input type="submit" class="btn dark" value="Check">
              </form>
            </div>

            <div class="sectionFilter__sub">
              <div class="sectionFilter__subName">Genre</div>
              <div class="sectionFilters__choices">
                <div class="filterChoice" @click="runFilter">RnB</div>
                <div class="filterChoice" @click="runFilter">Hip Hop</div>
                <div class="filterChoice" @click="runFilter">Rap</div>
                <div class="filterChoice" @click="runFilter">Classic</div>
                <div class="filterChoice" @click="runFilter">Classic</div>
                <div class="filterChoice" @click="runFilter">Classic</div>
                <div class="filterChoice" @click="runFilter">Classic</div>
                <div class="filterChoice" @click="runFilter">Classic</div>
              </div>
            </div>

        </div>
      </div>

      <div class="sectionFeed">
        <div class="userPostGenerate sectionElement">
          <!-- button for hiding the post-generator -->
          <!-- <div class="btn_activate_userPostGenerate">
          Post
        </div> -->
        <form class="userPostContainer" action="#" method="post">
          <input class="postText" type="text" name="postText" placeholder="Would you like to share something with the community?">
          <div class="userPostContainer__items">
            <div class="userPostContainer__items--left">
              <a href="#" class="btn mini">
                <svg><use xlink:href="../assets/symbol-defs.svg#icon-music"></use></svg>
              </a>
              <a href="#" class="btn mini">
                <svg><use xlink:href="../assets/symbol-defs.svg#icon-equalizer"></use></svg>
              </a>
              <a href="#" class="btn mini">
                <svg><use xlink:href="../assets/symbol-defs.svg#icon-cog"></use></svg>
              </a>
            </div>
            <div class="userPostContainer__items--right">
              <label>Share to:</label>
              <input type="checkbox" name="" value="">
              <label>Your community</label>
              <input type="checkbox" name="" value="">
              <label>Public</label>
              <input class="btn dark" type="submit" value="Post">
            </div>
          </div>
        </form>
      </div>

        <div class="feedElement sectionElement">
          <elementFeed></elementFeed>
        </div>

        <div class="feedElement sectionElement">
          <elementFeed></elementFeed>
        </div>

    </div>

  </div>
</div>
</template>

<script>
import FeedElement from '../components/FeedElement.vue';

export default {
  data(){
    return {
      title: 'Discover'
    }
  },
  components: {
    'elementFeed': FeedElement
  },
  methods: {
    showFilters: function() {
      let allFilters = document.querySelectorAll('.sectionFilter__sub');
      let filterContainer = document.querySelector('.sectionFilter.sectionElement');
      let filterButton = document.querySelector('.filterToggle');

      for (let i=0;i < allFilters.length; i++){
        if (allFilters[i].style.display == 'flex') {
          allFilters[i].style.display = 'none';
        } else {
          allFilters[i].style.display = 'flex';
        }
      }

      if (filterContainer.classList.contains("minWidth") == true) {
        filterContainer.classList.remove("minWidth");
      } else {
        filterContainer.classList.add("minWidth");
      }

      if (filterButton.classList.contains("noMargin") == true) {
        filterButton.classList.remove("noMargin");
      } else {
        filterButton.classList.add("noMargin");
      }
    },
    runFilter: function(event) {
      if (event.target.classList.contains("active") == true) {
        event.target.classList.remove("active");
      } else {
        event.target.classList.add("active");
      }
    }
  }
}
</script>

<style lang="css" scoped>
.sectionContainer {
  margin: 4rem 0 2rem 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.sectionChannels > * {
  min-width: 25rem;
  max-width: 60rem;
}
.sectionChannels {
  width: inherit;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
}
.sectionContainer > div,
.sectionFilter,
.userPostGenerate,
.feedElement {
  margin-bottom: 2rem;
  margin-right: 2rem;
}
.sectionFeed {
  width: 100%;
  margin-right: 2rem;
}


.sectionFilter {
  padding: 1rem 2rem;
}
.sectionFilter > * {
  margin-bottom: 1rem;
}
.sectionFilter.minWidth {
  width: min-content;
}
.filterToggle {
  font-size: 2rem;
  margin-bottom: 2rem;
  user-select: none;
  cursor: pointer;
}
.filterToggle.noMargin {
  margin-bottom: 0;
}
.sectionFilter__sub {
  /* default to none, but is flex */
  display: none;
  flex-direction: row;
}
.sectionFilter__sub:not(:last-of-type) {
  margin-bottom: 2rem;
}
.sectionFilter__subName {
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 1.6rem;
  margin: 0 1rem 1rem 0;
}
.sectionFilters__choices {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.filterChoice {
  display: flex;
  width: auto;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  text-align: left;
  padding: .6rem 1.5rem;
  margin: 0 1rem 1rem 0;
  border: 1px solid rgba(200,200,200,.4);
  border-radius: 2rem;
  transition: .2s;
}
.filterChoice svg,
.filterChoice__name {
  pointer-events: none;
}
.filterChoice.active {
  background-color: var(--color-btn-filter-active);
}
.filterChoice__name {
  width: min-content;
}
.filterChoice svg {
  height: 1.8rem;
  width: 1.8rem;
  fill: white;
  margin-right: .6rem;
}
.filterChoice:hover,
.filterChoice:active {
  background-color: var(--color-choice-hover);
  cursor: pointer;
}
.sectionFilter__sub form {
  display: flex;
  align-items: center;
}
.sectionFilter__sub .icon-search {
  position: relative;
  left: 2.8rem;
  fill: white;
  height: 1.8rem;
  width: 1.8rem;
}
.sectionFilter__sub .searchbar {
  height: 3rem;
  width: 100%;
  margin-right: 1rem;
  padding: 1rem 4rem;
  border-radius: 1.5rem;
  border: none;
  background-color: var(--color-element-darker);
}
.sectionFilter__sub .searchbar::placeholder {
  color: var(--color-text-placeholder);
}
.sectionFilter__sub .searchbar:hover,
.sectionFilter__sub .searchbar:active,
.sectionFilter__sub .searchbar:focus {
  outline: none;
}



.userPostGenerate {
  min-height: 8rem;
  width: 100%;
}
.userPostContainer {
  min-height: inherit;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.postText {
  height: 4rem;
  border: var(--main-border);
  border-radius: 1.3rem 1.3rem 0 0;
  padding: 2rem;
  background-color: var(--color-element-darker);
  color: var(--color-text);
  outline: none;
}
.postText::placeholder {
  color: var(--color-text-placeholder);
}
.userPostContainer__items {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-content: center;
  align-items: center;
  padding: 1rem 1.5rem;
}
.userPostContainer__items--left,
.userPostContainer__items--right {
  display: flex;
  flex-direction: row;
}
.userPostContainer__items--left > * {
  margin-right: 1rem;
}
.userPostContainer__items--right > *:not(:last-child) {
  margin-right: .6rem;
}
.userPostContainer__items--right label:last-of-type {
  margin-right: 2rem;
}
.userPostContainer__items--right label:first-of-type {
  margin-right: 2rem;
}
.userPostContainer__items--right {
  display: flex;
  align-items: center;
}
.btn.mini {
  border: 1px solid rgba(200,200,200,.4);
  height: 3rem;
  width: 3rem;
  border-radius: 5rem;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: .2s;
}
.btn.mini svg {
  fill: white;
  height: 2rem;
  width: 2rem;
}
.btn.mini:hover,
.btn.mini:active {
  background-color: var(--color-choice-hover);
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
.btn.dark:focus {
  outline: none;
}
</style>
