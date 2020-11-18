<template>
  <div id="app">

    <b-btn-group>
      <b-btn @click="showStart">Start</b-btn>
      <b-btn @click="showGame">Spielen</b-btn>
      <b-btn @click="showQuestionEdit">Fragen bearbeiten</b-btn>
    </b-btn-group>

      <b-container class="bv-example-row">
        <b-row class="text-center">
          <b-col></b-col>
          <b-col md="12">
            <br>
            <div id="start">
               <Start />
            </div>

            <div id="game">
               <Game />
            </div>

            <div id="editQuestions">
               <EditQuestions v-bind:ListOfQuestions=AllQuestions v-on:delete-question="DeleteQuestion"/>
            </div>

          </b-col>
          <b-col></b-col>
        </b-row>
      </b-container>
  </div>
</template>

<script>
import Start from './components/Start';
import Game from './components/Game';
import EditQuestions from './components/EditQuestions';

export default {
  name: 'App',
  components: {
    Start,
    Game,
    EditQuestions
  },
  data() {
    return {
      AllQuestions: [
        {
          pos : 0,
          title : "Eine Frage?",
          antwort1 : 515,
          antwort2 : 120,
          antwort3 : 50,
          antwort4 : 30,
          antwort5 : 2
        },
        {
          pos : 1,
          title : "Eine Frage?",
          antwort1 : 515,
          antwort2 : 120,
          antwort3 : 50,
          antwort4 : 30,
          antwort5 : 2
        }
      ]
    }
  },
  methods : {
    showStart(){
      document.getElementById("game").style.display = "none";
      document.getElementById("editQuestions").style.display = "none";
      document.getElementById("start").style.display = "inline";
    },
    showGame(){
      document.getElementById("game").style.display = "inline";
      document.getElementById("editQuestions").style.display = "none";
      document.getElementById("start").style.display = "none";
    },
    showQuestionEdit(){
      document.getElementById("game").style.display = "none";
      document.getElementById("editQuestions").style.display = "inline";
      document.getElementById("start").style.display = "none";
    },
    DeleteQuestion(positionQuestion){
        console.log("DEL")
        console.log(positionQuestion)
        this.AllQuestions = this.AllQuestions.filter(obj => obj.pos !== positionQuestion);
    }
  },
  mounted(){
      document.getElementById("game").style.display = "none";
      document.getElementById("editQuestions").style.display = "none";
      document.getElementById("start").style.display = "inline";
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
