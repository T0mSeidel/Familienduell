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
          <br />
          <div id="start">
            <Start />
          </div>

          <div id="game">
            <Game />
          </div>

          <div id="editQuestions">
            <EditQuestions
              v-bind:ListOfQuestions="AllQuestions"
              v-on:delete-question="DeleteQuestion"
              v-on:add-question="AddQuestion"
            />
          </div>
        </b-col>
        <b-col></b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Start from "./components/Start";
import Game from "./components/Game";
import EditQuestions from "./components/EditQuestions";

export default {
  name: "App",
  components: {
    Start,
    Game,
    EditQuestions,
  },
  data() {
    return {
      AllQuestions: [{title:"Gemüse?",pos:1, antwort1:10, antwort1_bezeichnung:"Kartoffel",antwort2:8, antwort2_bezeichnung:"Brokkoli", antwort3:6, antwort3_bezeichnung:"Kohl", antwort4:3, antwort4_bezeichnung:"Wirsing",antwort5:10, antwort5_bezeichnung:"Knoblauch"}, {title:"Obst?",pos:2, antwort1:10, antwort1_bezeichnung:"Apfel",antwort2:8, antwort2_bezeichnung:"Birne", antwort3:6, antwort3_bezeichnung:"Banane", antwort4:3, antwort4_bezeichnung:"Tomate",antwort5:10, antwort5_bezeichnung:"Rahbarba"}],
    };
  },
  methods: {
    showStart() {
      document.getElementById("game").style.display = "none";
      document.getElementById("editQuestions").style.display = "none";
      document.getElementById("start").style.display = "inline";
    },
    showGame() {
      document.getElementById("game").style.display = "inline";
      document.getElementById("editQuestions").style.display = "none";
      document.getElementById("start").style.display = "none";
    },
    showQuestionEdit() {
      document.getElementById("game").style.display = "none";
      document.getElementById("editQuestions").style.display = "inline";
      document.getElementById("start").style.display = "none";
    },
    DeleteQuestion(positionQuestion) {
      console.log("DEL");
      console.log(positionQuestion);
      this.AllQuestions = this.AllQuestions.filter(
        (obj) => obj.pos !== positionQuestion
      );
    },
    AddQuestion(question) {
      console.log("ADD");
      console.log(question);
      this.AllQuestions.push(question);
    },
  },
  mounted() {
    document.getElementById("game").style.display = "none";
    document.getElementById("editQuestions").style.display = "none";
    document.getElementById("start").style.display = "inline";
  },
};
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
