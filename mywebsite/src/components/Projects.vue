<template>
    <div>
        <h1>My projects</h1>
        <div class="projects" v-for="project in projects">
            <div class="image"><img v-bind:src="`../media/project_images/${project.id}.png`"></div>
            <h3>{{ project.title }}</h3>
            <p>{{ project.description }}</p>
            <table>
              <tr>
                <th>Programming language: </th>
                <td>{{ project.programmingLanguage}}</td>
              </tr>
              <tr>
                <th>Technologies used: </th>
                <td>{{ project.technologies}}</td>
                
              </tr>
              <tr>
                <th>Link: </th>
                <td><a href="#"> {{ project.link}}</a></td>
              </tr>
            </table>
        </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
          {
            id: 0, 
            title: 'PyKimble', 
            programmingLanguage: "Python", 
            technologies: "PyGame", 
            description: 'Kimble is a Finnish board game. This is still unfinished version and should have online mode. Programmed with Python using PyGame-library.', 
            link: "https://github.com/JoonasHeinonen/PyKimble"
          },
          {
            id: 1, 
            title: 'PyCarShooter', 
            programmingLanguage: "Python", 
            technologies: "PyGame", 
            description: 'A car shooter game programmed with Python using PyGame-library. Very simple one.', 
            link: "https://github.com/JoonasHeinonen/PyCarShooter"
          },
          {
            id: 2, 
            title: 'Romance Game',
            programmingLanguage: "C#", 
            technologies: "Unity 2D", 
            description: 'A game based loosely on Goofy Movie. It is an adventure game where you do quests in an urban environment.', 
            link: "https://github.com/JoonasHeinonen/Romance_Game"
          },
          {
            id: 3, 
            title: 'Vue-Yatzy',
            programmingLanguage: "JavaScript", 
            technologies: "Vue.js", 
            description: 'Simple dice game implemented with Vue.js and programmed using JavaScript. Keeps up scoring. Has an GitHub-environment for it.', 
            link: "https://github.com/JoonasHeinonen/Vue-Yatzy"
          }
      ]
    }
  },
  methods: {
    aFunction: function () {

    }
  }
}
</script>

<style scoped>
  h3 {
    text-align: center;
  }
  .image, img {
    margin: 0px auto;
    max-width: 300px;
    max-height: 300px;
  }
  p, th {
    text-align: justify;
  }
  th, td, tr {
    font-size: 12px;
  }
  .projects *{
    box-sizing: border-box;
  }
  .projects, table {
    width: 100%;
  }
  .projects {
    background-color: white;
    border: 1px solid lightgrey;
    margin: 20px auto;
    max-width: 500px;
    padding: 20px;
  }
  label {
      display: block;
      margin: 20px 0 10px;
  }
  input[type="text"], textarea {
      display: block;
      width: 100%;
      padding: 8px;
      resize: none;
  }
  h3 {
      margin-top: 10px
  }
</style>