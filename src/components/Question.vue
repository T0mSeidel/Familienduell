<template>
  <div class="question-item">
    <br />
    <b-form-group>
      <button
        type="button"
        class="close"
        aria-label="Close"
        @click="$emit('delete-question', question)"
      >
        <span aria-hidden="true">&times;</span>
      </button>

      <h2>{{ question.title }}</h2>

      <br />

      <b-form-input size="sm" v-model="question.title"></b-form-input>

      <br />

      <b-form inline>
        <b-form-group
          label-cols-sm="2"
          label="Position Frage"
          label-for="inline-form-input-position"
        >
          <b-input id="inline-form-input-position" v-model="question.pos">
          </b-input>
        </b-form-group>

        <b-form-group
          label-cols-sm="2"
          label="Antwort Platz 1"
          label-for="inline-a1"
        >
          <b-input
            id="inline-a1"
            v-model="question.antwort1"
            placeholder="Anzahl der Antwort"
          >
          </b-input>
          <b-input
            antwort1_bezeichnung="inline-a1-bezeichnung"
            v-model="question.antwort1_bezeichnung"
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
            v-model="question.antwort2"
            placeholder="Anzahl der Antwort"
          >
          </b-input>
          <b-input
            antwort2_bezeichnung="inline-a2-bezeichnung"
            v-model="question.antwort2_bezeichnung"
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
            v-model="question.antwort3"
            placeholder="Anzahl der Antwort"
          >
          </b-input>
          <b-input
            antwort3_bezeichnung="inline-a3-bezeichnung"
            v-model="question.antwort3_bezeichnung"
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
            v-model="question.antwort4"
            placeholder="Anzahl der Antwort"
          >
          </b-input>
          <b-input
            antwort4_bezeichnung="inline-a4-bezeichnung"
            v-model="question.antwort4_bezeichnung"
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
            v-model="question.antwort5"
            placeholder="Anzahl der Antwort"
          >
          </b-input>
          <b-input
            antwort5_bezeichnung="inline-a5-bezeichnung"
            v-model="question.antwort5_bezeichnung"
            placeholder="Antwort hier eingeben"
          >
          </b-input>
        </b-form-group>
      </b-form>
      <br />
    </b-form-group>
  </div>
</template>

<script>
export default {
  name: "Question",
  props: ["question"],
  methods: {},
};
</script>

<style scoped>
.question-item {
  padding: 8px;
  border-bottom: 1px #ccc solid;
}
</style>