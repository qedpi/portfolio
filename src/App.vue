<template>
  <div id="app">
    <transition name="fade">
      <div v-if="fully_rendered">
        <header>
          <portfolio-header></portfolio-header>
        </header>

        <nav class="navbar navbar-inverse bg-inverse">
          <a class="navbar-brand" href="#">
            <img id="logo" src="./assets/logo.png">
          </a>
          <ul class="navbar-nav mr-auto" id="nav-items">
            <li v-for="nav_option of nav_options"
                @click="nav_selected = nav_option"
                :class="{'nav-selected': nav_selected === nav_option}" class="nav-item">
              <a href="#" class="nav-link">
                {{nav_option}}
              </a>
            </li>
          </ul>
        </nav>

        <transition name="fade">
          <portfolio-projects v-if="nav_selected === 'Projects'"></portfolio-projects>
          <portfolio-skills v-else-if="nav_selected === 'Skills'"></portfolio-skills>
        </transition>

      </div>
    </transition>
  </div>
</template>

<script>
  import PortfolioHeader from './PortfolioHeader.vue'
  import PortfolioProjects from './PortfolioProjects.vue'
  import PortfolioSkills from './PortfolioSkills.vue'

  export default {
    name: 'app',
    components: {
      PortfolioHeader,
      PortfolioProjects,
      PortfolioSkills,
    },
    data() {
      return {
        fully_rendered: false,
        nav_options: ['Projects', 'Skills', 'Tech Journal', 'Youtube', 'Creative'],
        nav_selected: 'Skills',
        nav_selected_style: {'border': 'lightgreen .1em solid'},
      }
    },
    methods: {

    },
    mounted(){
      this.fully_rendered = true;
    },
  }
</script>

<style lang="scss">
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }

  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
  }
  .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0;
  }

  #logo {
    height: 3rem;
  }

  nav {
    margin-top: -1rem;
  }

  .navbar-nav {
    display: inline;
  }

  .nav-selected {
    border-bottom: lightgreen .1em solid;
  }

  #nav-items {
    color: lightgreen;
  }

  .nav-item {
    font-size: 20px;
  }

  .nav-item:hover {
    border-bottom: lightblue .1em solid;
  }

</style>
