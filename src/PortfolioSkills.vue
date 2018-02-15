<template>
  <div>
    <div class="wrapper container">
      <template v-for="(skill_group, label) in skills">
        <div class="card">
          <h1 class="card-title bg-success text-white text-center display-4 skills">
            {{label}}
          </h1>
          <div>
            <template v-for="(prof, skill) in skill_group">
              <div class="skill-wrapper">
                <p>
                  {{skill}}:
                </p>
                <div>
                  <template v-for="_ in prof">
                    <i :class=icons[skill]></i> &nbsp;
                  </template>
                </div>
              </div>
            </template>
          </div>
        </div>
      </template>
    </div>
  </div>
</template>

<script>
  export default {
    name: "portfolio-skills",
    data(){
      return {
        icons: {
          'Vue.js': 'fab fa-vuejs',
          'Django': 'fab fa-python',
          'JS / ES7': 'fab fa-js',
          'HTML5': 'fab fa-html5',
          'CSS3': 'fab fa-css3-alt',

          'Pandas': 'fab fa-python',
          'SQL': 'fab fa-python',
          'NumPy & SciPy': 'fab fa-python',
          'Matplotlib': 'fab fa-python',
          'Jupyter': 'fab fa-python',
        },
        skills: {
          'Web Development': {'Vue.js': 2, 'Django': 2, 'JS / ES7': 3, 'HTML5': 2, 'CSS3': 1},
          'Data Science': {'Pandas': 1, 'SQL': 1, 'NumPy & SciPy': 1, 'Matplotlib': 1, 'Jupyter': 0},
          'Machine Learning': {'Tensorflow': 1, 'scikit-learn': 0},
          'Theory': {'Algorithms & Data Structures': 3, 'Statistics': 1, 'Calculus': 2, 'Linear Algebra': 1},
        }
      }
    },
  }
</script>

<style scoped>
  .wrapper {
    display: grid;
    grid-template-columns: repeat(2, 45%);
    grid-gap: 10%;
  }

  .card {
    margin-bottom: 2em;
  }

  .skills {
    font-size: 35px;
  }

  .skill-wrapper {
    display: grid;
    grid-template-columns: 30% 60%;
    grid-gap: 10%;
  }
</style>
