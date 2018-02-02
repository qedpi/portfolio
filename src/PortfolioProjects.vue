<template>
  <div>
    <div class="container container-fluid">
      <transition name="fade">
        <!--<template v-for="project in projects" v-if="project.name === project_names[project_id]">-->
        <template v-if="toggle_project">
          <div id="projects">
            <!-- Left / Top Panel -->
            <div id="info" class="card">
              <h1 class="card-title bg-success text-white text-center display-4">
                {{project.name}}
              </h1>
              <ul class="desc">
                <p v-for="sentence of project.desc" class="lead">
                  {{sentence}}
                </p>
              </ul>
              <div class="card-footer text-muted">
                <ul>
                  <li v-for="tag in project.tags">#{{tag}}</li>
                </ul>
              </div>
            </div>

            <!-- Right / Bottom Panel -->
            <div class="card">
              <img :src="project.src" class="fitpic">
              <hr>
              <div id="icons">
                <a :href="project.git" target="_blank">
                  <i class="fa fa-github"></i>
                </a>
                <a :href="project.website" target="_blank">
                  <i class="fa fa-link"></i>
                </a>
              </div>
            </div>
          </div>
        </template>
      </transition>
    </div>
  </div>
</template>

<script>
  export default {
    name: "portfolio-jumbotron",
    data() {
      return {
        toggle_project: true,
        project_id: 0,
        project_names: ['SongCards', 'ArithMetrics', 'BabelMatch'],
        projects: [
          {
            name: 'SongCards',
            src: "src/assets/projects/SongCards.jpg",
            git: 'https://github.com/qedpi/SongCards',
            website: 'https://songcards.herokuapp.com',
            desc: [
              'Spaced Repetition for songs:',
              'Scrapes lyrics & tabs,',
              'Colored & transposable chords',
              'Search cards & share with friends',
              'Control autoscroll speed',
            ],
            tags: ['Python', 'Django', 'SQLite', 'Bootstrap', 'jQuery', 'Heroku', 'Webpack'],
          },
          {
            name: 'ArithMetrics',
            src: "src/assets/projects/ArithMetrics.jpg",
            git: 'https://github.com/qedpi/ArithMetrics',
            website: 'https://qedpi.github.io/ArithMetrics/',
            desc: [
              'Practice mental arithmetic:',
              'Choose operators to use',
              'Randomized operators & operands',
              'Adjust digits / difficulty',
              'Set daily goal',
            ],
            tags: ['Vue.js', 'Bootstrap', 'JavaScript', 'HTML', 'CSS'],
          },
          {
            name: 'BabelMatch',
            src: "src/assets/projects/ArithMetrics.jpg",
            git: 'https://github.com/qedpi/babel-chat',
            website: 'https://babelmatch.herokuapp.com/',
            desc: [
              'Chat with a stranger:',
              'Translate to their language',
              'Hear their messages with Text-to-speech',
              'Doodle on the side panel',
              'Join lobby & see users online',
            ],
            tags: ['Vue.js', 'Socket.io', 'google-translate', 'Text-to-speech', 'Bootstrap', 'JavaScript'],
          },
        ],
      }
    },
    mounted(){
      setInterval(() => {
        this.project_id = (this.project_id + 1) % this.project_names.length;
        this.toggle_project = false;
        setTimeout(() => this.toggle_project = true, 500);
      }, 10000)
    },
    computed: {
      project(){
        return this.projects[this.project_id];
      },
    }
  }
</script>

<style scoped lang="scss">
  .fitpic {
    width: 100%;
    height: 290px;
  }

  #projects {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    grid-gap: 4%;
  }

  #info {
    text-align: left;
  }

  #icons {
    font-size: 3rem;
    .fa {
      margin-left: 1rem;
      margin-right: 1rem;
    }
  }

  .card {
    border-radius: 20%;
    overflow: hidden;
  }

  #info {
    text-align: center;
  }

  .desc {
    margin-top: 1em;
  }

  .desc p {
    color: darkgreen;
  }

</style>
