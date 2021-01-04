<template>
  <div>
    <b-form-group>
      <br />

      <b-form-input
        size="sm"
        v-model="title"
        placeholder="Hier Frage eingeben"
      ></b-form-input>

      <br />

      <b-form inline>
        <b-form-group
          label-cols-sm="2"
          label="Position Frage"
          label-for="inline-form-input-position"
        >
          <b-input id="inline-form-input-position" v-model="pos"> </b-input>
        </b-form-group>

        <b-form-group
          label-cols-sm="2"
          label="Antwort Platz 1"
          label-for="inline-a1"
        >
          <b-input
            id="inline-a1"
            v-model="antwort1"
            placeholder="Anzahl der Antwort"
          >
          </b-input>
          <b-input
            antwort1_bezeichnung="inline-a1-bezeichnung"
            v-model="antwort1_bezeichnung"
            placeholder="Antwort hier eingeben"
          >
          </b-input>
        </b-form-group>

        <b-form-group
          label-cols-sm="2"
          label="Antwort Platz 2"
          label-for="inline-a2"
        >
          <b-input
            id="inline-a2"
            v-model="antwort2"
            placeholder="Anzahl der Antwort"
          >
          </b-input>
          <b-input
            antwort2_bezeichnung="inline-a2-bezeichnung"
            v-model="antwort2_bezeichnung"
            placeholder="Antwort hier eingeben"
          >
          </b-input>
        </b-form-group>

        <b-form-group
          label-cols-sm="2"
          label="Antwort Platz 3"
          label-for="inline-a3"
        >
          <b-input
            id="inline-a3"
            v-model="antwort3"
            placeholder="Anzahl der Antwort"
          >
          </b-input>
          <b-input
            antwort3_bezeichnung="inline-a3-bezeichnung"
            v-model="antwort3_bezeichnung"
            placeholder="Antwort hier eingeben"
          >
          </b-input>
        </b-form-group>

        <b-form-group
          label-cols-sm="2"
          label="Antwort Platz 4"
          label-for="inline-a4"
        >
          <b-input
            id="inline-a4"
            v-model="antwort4"
            placeholder="Anzahl der Antwort"
          >
          </b-input>
          <b-input
            antwort4_bezeichnung="inline-a4-bezeichnung"
            v-model="antwort4_bezeichnung"
            placeholder="Antwort hier eingeben"
          >
          </b-input>
        </b-form-group>

        <b-form-group
          label-cols-sm="2"
          label="Antwort Platz 5"
          label-for="inline-a5"
        >
          <b-input
            id="inline-a5"
            v-model="antwort5"
            placeholder="Anzahl der Antwort"
          >
          </b-input>
          <b-input
            antwort5_bezeichnung="inline-a5-bezeichnung"
            v-model="antwort5_bezeichnung"
            placeholder="Antwort hier eingeben"
          >
          </b-input>
        </b-form-group>
      </b-form>
      <br />
      <b-button variant="success" v-on:click="add">Hinzufügen</b-button>
    </b-form-group>
  </div>
</template>

<script>
export default {
  name: "AddQuestion",
  data() {
    return {
      pos: 0,
      title: "",
      antwort1: 0,
      antwort1_bezeichnung: "",
      antwort2: 0,
      antwort2_bezeichnung: "",
      antwort3: 0,
      antwort3_bezeichnung: "",
      antwort4: 0,
      antwort4_bezeichnung: "",
      antwort5: 0,
      antwort5_bezeichnung: "",
    };
  },

  props: ["questions"],

  methods: {
    add: function (e) {
      e.preventDefault();

      const newQuestion = {
        pos: this.pos,
        title: this.title,
        antwort1: this.antwort1,
        antwort1_bezeichnung: this.antwort1_bezeichnung,
        antwort2: this.antwort2,
        antwort2_bezeichnung: this.antwort2_bezeichnung,
        antwort3: this.antwort3,
        antwort3_bezeichnung: this.antwort3_bezeichnung,
        antwort4: this.antwort4,
        antwort4_bezeichnung: this.antwort4_bezeichnung,
        antwort5: this.antwort5,
        antwort5_bezeichnung: this.antwort5_bezeichnung,
      };
      this.$emit("add-question", newQuestion);
    },
  },
};
</script>

<style scoped>
</style>